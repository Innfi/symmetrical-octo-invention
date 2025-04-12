 #DNS #Security #Mail 

Domain-based Message Authentication Reporting and Conformance

v=dmarc1;
p=quantine; / p=none; / p=reject;
adkim=s; (strict) / adkim=r; (relaxed)
aspf=s; / aspf=r;

strict / relaxed: alignment

strict: demands an exact match between the domain in the “From” address of the email and the domain authenticated by spf and/or dkim

relaxed: the domain in the “From” address must match the authenticated domain at the organizational level. emails sent from a subdomain can still pass DMARC checks even if they don’t match the exact domain used in SPF or DKIM authentication

rua: aggregate report
ruf: forensic report


Example.com's DMARC policy might look like this:

|Name|Type|Content|TTL|
|---|---|---|---|
|`_dmarc.example.com`|`TXT`|`v=DMARC1; p=quarantine; adkim=r; aspf=r; rua=mailto:example@third-party-example.com;`|`32600`|

Within this TXT record, the DMARC policy is contained in the "Content" field.