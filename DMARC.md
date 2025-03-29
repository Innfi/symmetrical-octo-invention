 #DNS #Security #Mail 

Domain-based Message Authentication Reporting and Conformance

v=dmarc1;
p=quantine; / p=none; / p=reject;
adkim=s; (strict) / adkim=r; (relaxed)
aspf=s; / aspf=r;


Example.com's DMARC policy might look like this:

|Name|Type|Content|TTL|
|---|---|---|---|
|`_dmarc.example.com`|`TXT`|`v=DMARC1; p=quarantine; adkim=r; aspf=r; rua=mailto:example@third-party-example.com;`|`32600`|

Within this TXT record, the DMARC policy is contained in the "Content" field.