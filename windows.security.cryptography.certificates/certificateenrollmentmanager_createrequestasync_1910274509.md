---
-api-id: M:Windows.Security.Cryptography.Certificates.CertificateEnrollmentManager.CreateRequestAsync(Windows.Security.Cryptography.Certificates.CertificateRequestProperties)
-api-type: winrt method
---

<!-- Method syntax
public Windows.Foundation.IAsyncOperation<string> CreateRequestAsync(Windows.Security.Cryptography.Certificates.CertificateRequestProperties request)
-->

# Windows.Security.Cryptography.Certificates.CertificateEnrollmentManager.CreateRequestAsync

## -description
Asynchronously creates a PKCS #10 certificate request based on properties specified in a [CertificateRequestProperties](certificaterequestproperties.md) object.

## -parameters
### -param request
A [CertificateRequestProperties](certificaterequestproperties.md) object that contains the property values used to create the certificate request.

## -returns
This method returns a string that contains the base64 encoded PKCS #10 certificate request.

## -remarks
Certificate enrollment can be performed in an app container. We recommend that you use the following request objects to submit the request:


+ [XMLHttpRequest](XREF:TODO:ie.XMLHttpRequest_Object) (JavaScript)
+ [HttpWebRequest](https://msdn.microsoft.com/library/system.net.httpwebrequest.aspx) (C#)
+ [IXMLHTTPRequest](XREF:TODO:63409298-0516-437d-b5af-68368157eae3) (C++)
The [CertificateRequestProperties](certificaterequestproperties.md) object contains the following default values.

<table>
   <tr><th>Property</th><th>Default value</th></tr>
   <tr><td>[Subject](certificaterequestproperties_subject.md)</td><td>Empty string</td></tr>
   <tr><td>[KeyAlgorithmName](certificaterequestproperties_keyalgorithmname.md)</td><td>RSA</td></tr>
   <tr><td>[KeySize](certificaterequestproperties_keysize.md)</td><td>2048 bits</td></tr>
   <tr><td>[FriendlyName](certificaterequestproperties_friendlyname.md)</td><td>Empty String</td></tr>
   <tr><td>[HashAlgorithmName](certificaterequestproperties_hashalgorithmname.md)</td><td>SHA256</td></tr>
   <tr><td>[Exportable](certificaterequestproperties_exportable.md)</td><td>Not Exportable</td></tr>
   <tr><td>[KeyUsages](certificaterequestproperties_keyusages.md)</td><td>Signing</td></tr>
   <tr><td>[KeyProtectionLevel](certificaterequestproperties_keyprotectionlevel.md)</td><td>NoConsent</td></tr>
   <tr><td>[KeyStorageProviderName](certificaterequestproperties_keystorageprovidername.md)</td><td>Microsoft Software Key Storage Provider</td></tr>
</table>

While the [CreateRequestAsync](certificateenrollmentmanager_createrequestasync.md) method creates the certificate request, you will need to submit the request to an http enrollment end point. You can then take the response from the http enrollment end point and then call the [InstallCertificateAsync](certificateenrollmentmanager_installcertificateasync.md) method to install the response.



> [!NOTE]
> You must include the **Signing** value in the [KeyUsages](certificaterequestproperties_keyusages.md) property in any[ CertificateRequestProperties](certificaterequestproperties.md) object that you use in a call to **CreateRequestAsync**. If you wish to set [KeyUsages](certificaterequestproperties_keyusages.md) to **Decryption** or **KeyAgreement**, you must also OR in **Signing**. Otherwise, the call to **CreateRequestAsync** will fail.

## -examples

## -see-also
