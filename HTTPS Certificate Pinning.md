# HTTPS Certificate Pinning

tags: #http #cert

Launching an MiTM attack by bypassing certificate pinning is a very complex client-side procedure. An attacker would first need physical access to the targeted mobile device and app. From there, he or she would need to root or jailbreak the device and reverse engineer, modify, and rewrite the functions performing cert pinning in the app. In the end, bypassing certificate pinning is much more difficult than executing the type of attacks certificate pinning guards against.

As part of good coding hygiene, all Android and iOS developers should implement certificate pinning for apps that handle sensitive data as a countermeasure against MiTM attacks. This minimal degree of additional effort yields significant protection. However, developers must be sure to implement pinning correctly so they’re not left with a false sense of security.

Cert pinning is imperative for any mobile app that exchanges sensitive data like credentials, financial information, business transactions, and PII. This includes mobile apps such as banking, healthcare, retail, utility, automotive, ERP/CRM, and IoT. In short, this encompasses most apps that do anything more than surface public data.



## Links

- [Preventing Man-in-the-Middle Attacks in iOS with SSL Pinning](https://www.raywenderlich.com/1484288-preventing-man-in-the-middle-attacks-in-ios-with-ssl-pinning)
- [Identity Pinning: How to configure server certificates for your app](https://developer.apple.com/news/?id=g9ejcf8y)
- [Certificate Pinning on Mobile Applications](https://www.perimeterx.com/tech-blog/2018/certificate-pinning-on-mobile/)
- [Securing Mobile Applications With Cert Pinning](https://dzone.com/refcardz/securing-mobile-applications-with-cert-pinning)
- [Mobile Certificate Pinning Generator](https://approov.io/tools/static-pinning/)
- [https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/Pinning_Cheat_Sheet.md](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/Pinning_Cheat_Sheet.md)