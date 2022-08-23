# XML Index

When using XML to select records based on an XML value the speed difference is usually not noticible.  However, when trying to use XML value for an "ORDER BY" clause the speed is often not acceptable on large database.  

If you have a small database then a direct XML "order by" will be good enough.  On large databases where the speed is not good you can use XML indexing to make the query quick.  

## Creating an XML index definition  

To create an index the fields must be defined in the "system.rules" file.  
An XML definition of the index should be defined, this definition is used to create "SYSTEMLINK%" records in the database, these records tell the indexing system what needs doing.

Examnple:  
```
    <sqlindex list="true">
	    <genxml>
		    <systemkey>RocketERMSmeeting</systemkey>
		    <ref>meetingdate</ref>
		    <xpath>genxml/textbox/date</xpath>
		    <typecode>RocketERMSmeetingART</typecode>
	    </genxml>
    </sqlindex>
```
*The XML node should be placed under the "genxml" node.  "genxml/sqlindex".*

**genxml/ref**: This is the database joined table name that will be used in code and by any SPROC call.
**genxml/xpath**: This is the xpath of the data field.  It identifies what data should be put into the index.  
**genxml/typecode**: The interface Entity TypeCode, this is the main data source record.  
**genxml/systemkey**: The is the system or plugin systemkey, it is used to identify when a index should be build, during record update.  

## How the definition is used  
On installation the "system.rules" file is moved to the "plugin" folder of the parent system.  Each plugin will have a sub-folder.  

The definition in the "system.rules" file is read from the plugin sub-folder on application start.  The index is then added to the database, by creating the "SYSTEMLINK%" records previously mentioned.  

**For the indexes to be created the reindex method must be called on the record update**
Example:
```
        public int Update()
        {
            _info = _objCtrl.SaveData(_info, _tableName);
            _objCtrl.RebuildIndex(_info.PortalId, _info.ItemID, "RocketERMSmeetingmeeting", _tableName);
            return _info.ItemID;
        }
```
The reindex method can be called at any point, but it's usually only required on the update method.

## Using the XML Index
The XML indexes are added as linked tables that use the "GUIDKey" column of the XML table to store the value.  Becuase the GUIDKey is an index column, and "order by" or selection for this data will operate with the same performace as a normal indexed column in the table.

Example selection:  
```
filter += " and meetingdate.GuidKey like '%" + searchtext + "%'";
```
Example Order By:
```
var sqlOrderBy = " order by meetingdate.GUIDKey desc ";
```
*NOTE: The index field always uses the “GuidKey” to store data and hence it is this DB column that will need to be used.  Be careful not to have genxml/ref duplicates in the system*




## When to create an index
Index records are designed to make the database selection and sorting faster, but keep in mind that, like any database, creating indexes does have a performance affect.   

All columns apart from the XML are already index by SQL server, hence the reason we use the GUIDKey field.

