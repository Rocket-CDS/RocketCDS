# Rocket CDS

**Rocket CDS** is a free, open-source suite of modules designed for fast and efficient data delivery.

Rocket CDS is a flexible and scalable **Content Delivery System (CDS)** integrated with the leading Microsoft open-source CMS. It provides the tools needed to quickly build data-driven systems and websites while maintaining a streamlined development workflow.

The platform focuses on simplicity and usability, offering an intuitive user experience that helps developers and administrators work more efficiently.

---

## Website

https://www.rocket-cds.org/

---

### Recommended Security Configuration (Optional)

The temporary upload folder may contain sensitive files. If the upload process fails after a file has been uploaded, those files may remain in the temporary directory and could potentially be accessed publicly.  
To reduce this risk, it is recommended to block public access to the temporary upload folder by returning a **403 Forbidden** response.  

*NOTE: This is not needed on v1.8.0 and above*

---

#### Create a Rule in the URL Rewrite Module

You can add the rule to either:

- `web.config`, or  
- `applicationHost.config`

Choose the location that best fits your server configuration.

```xml
<rule name="Block DNNrocketTemp Access" stopProcessing="true">
  <match url=".*" />
  <conditions>
    <add input="{REQUEST_URI}" pattern="DNNrocketTemp" ignoreCase="true" />
  </conditions>
  <action type="CustomResponse" statusCode="403" statusReason="Forbidden" statusDescription="Access Denied" />
</rule>
