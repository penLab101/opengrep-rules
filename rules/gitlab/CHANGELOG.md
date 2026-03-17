sast-rules changelog

## v2.9.2
- Update `rules/lgpl/javascript/ssrf/rule-node_ssrf.yml` rule to reduce False Negatives (!703)

## v2.9.1
- Fix rules that are no longer valid as of semgrep >= 1.128.0 by adding explicit type metavariables (!711)

## v2.9.0
- Update constant DB password rules for Java, Kotlin and Scala to not catch empty strings (!702)
- Update `java/smtp/rule-InsecureSmtp.yml` to fix false-positives (!704)

## v2.8.4
- Update `rules/lgpl/javascript/dos/rule-layer7_object_dos.yml` and test cases to detect use of `slice()` method to limit input processing (!701)
- Add `rules/gitlab/kotlin/pathtraversal/rule-FilePathTraversal.yml` to detect Kotlin Path Traversal vulnerabilities (!700)

## v2.8.3
- Add `rules/gitlab/generic/injection/bidi/rule-BiDiTrojanSource.yml` following review (!695)
- Update `python/sql/rule-hardcoded-sql-expression.yml` for better performance (!696)

## v2.8.2
- Remove `rules/gitlab/generic/injection/bidi/rule-BiDiTrojanSource.yml` due to performance concerns (!694)

## v2.8.1
- Fix broken build release process (!688)

## v2.8.0
- Update metadata (severity and CWE mappings) for some rules (!665)
- Split `javascript_buf_rule-buffer-noassert` rule into two more specific and narrower rules (!665)
- Remove duplicate rule `rules_lgpl_javascript_memory_rule-buffer-noassert` (!665)
- Update `rule-SqlInjection.yml` to assume numbers and booleans cannot contain taint (!668)
- Update `python_escaping_rule-jinja2-autoescape-false` rule to enhance patterns (!609)
- Update `rules_lgpl_javascript_ssrf_rule-node-ssrf` rule to enhances patterns to reduce False Positives (!663)
- Update `rules_lgpl_javascript_ssrf_rule-node-ssrf` rule to enhance fetch api patterns to reduce False Positives (!662)
- Update `java_crypto_rule-CipherPaddingOracle`, `java_crypto_rule-CipherIntegrity` and `java_crypto_rule-CipherECBMode` rules to enhance patterns (!646)
- Add `rules/gitlab/generic/injection/bidi/rule-BiDiTrojanSource.yml` (!681)
- Add `rules/lgpl-cc/yaml/spring/accesscontrol/rule-SpringActuatorFullyEnabled` to detect vulnerable spring actuator configuration in `*.yaml` and `*.yml` files (!675)
- Add `rules/lgpl-cc/properties/spring/accesscontrol/rule-SpringActuatorFullyEnabled` to detect vulnerable spring actuator configuration in `*.properties` files (!675)
- Update `python_sql_rule-hardcoded-sql-expression` rule to reduce False Positives (!684)
- Update `csharp_injection_rule-SQLInjection` rule to increase coverage (!679)
- Add `rules/gitlab/java/deserialization/rule-InsecureDeserialization.yaml` (!678)


## v2.7.0
- Remove rule `python/exec/rule-paramiko-calls.yml` to reduce FPs (!661)

## v2.6.0
- Fix markdown rendering in vulnerability reports (!658)
- Updating CWEs in accordance with MITRE guidelines (!656)
- Update `rule-express_xss.yml` to reduce FPs (!657)
- Update `python_deserialization_rule-dill` (!610)
- Update `csharp_injection_rule-LdapInjection` and `javascript_exec_rule-child-process` to support semgrep 1.75 and above (!659)

## v2.5.8
- Fix `rules/lgpl/javascript/dos/rule-layer7_object_dos.yml` to work on semgrep 1.75 or later (!648)
- Update from community contributor `rules/lgpl/javascript/database/rule-node_nosqli_injection.yml` to reduce FPs where inputs have been cast to strings (!653)
- Update `go/filesystem/rule-ziparchive.yml` fixes description recommendation (!636)

## v2.5.7
- Fix `java/inject/rule-SpotbugsPathTraversalAbsolute.yml` to be less FP prone (!642)

## v2.5.6
- Update `java/crypto/rule-BlowfishKeySize.yml` to cast key size to integer before comparing (!637)
- Update `java/crypto/rule-CipherDESInsecure.yml` to detect DES ciphers from default property values (!637)
- Update `java/crypto/rule-CipherDESedeInsecure.yml` to detect DESede ciphers from default property values (!637)
- Update `java/crypto/rule-CipherECBMode.yml` to detect ciphers in ECB mode from default property values (!637)
- Update `java/crypto/rule-CipherIntegrity.yml` to detect ciphers without message integrity from default property values (!637)
- Update `java/crypto/rule-CipherPaddingOracle.yml` to detect vulnerable ciphers from default property values (!637)
- Update `java/crypto/rule-RsaNoPadding.yml` to detect vulnerable ciphers from default property values (!637)
- Update `java/crypto/rule-WeakMessageDigest.yml` to detect weak algorithms from default property values (!637)
- Update `java/crypto/rule-WeakTLSProtocolDefaultHttpClient.yml` to remove unnecessary `pattern-either` (!637)
- Update `java/crypto/rule-WeakTLSProtocolSSLContext.yml` to detect weak protocols from default property values (!637)
- Update `java/inject/rule-CommandInjection.yml` to enhance patterns and use taint mode (!637)
- Update `java/inject/rule-SpotbugsPathTraversalAbsolute.yml` to enhance patterns (!637)
- Update `java/xss/rule-XSSReqParamToServletWriter.yml` to enhance patterns (!637)
- Update `rules/lgpl-cc/java/inject/rule-SqlInjection.yml` to enhance patterns (!637)

## v2.5.5
- Remove `java/random/rule-PseudoRandom.yml` rule (!635)
- Remove `rules/lgpl/kotlin/random/rule-PseudoRandom.yml` rule (!635)
- Remove `scala/random/rule-PseudoRandom.yml` rule (!635)

## v2.5.4
- Add `rules/lgpl-cc/java/inject/rule-EnvInjection.yml` (!565)
- Add `rules/lgpl-cc/python/crypto/rule-HTTPConnectionPool.yml` (!589)
- Add `rules/lgpl-cc/python/flask/security/redirection/rule-flask-open-redirect.yml` (!577)
- Add `java/crypto/rule-WeakTLSProtocolSSLContext.yml` (!401)
- Add `rules/lgpl-cc/java/crypto/rule-HttpComponentsRequest.yml` (!582)
- Remove `java/password/rule-HardcodeKeyEquals.yml` as secret detection should be used instead. (!607)
- Remove `rules/lgpl-cc/java/password/rule-HardcodeKey.yml` as secret detection should be used instead. (!607)
- Remove `rules/gitlab/scala/password/rule-HardcodeKey.yml` as secret detection should be used instead. (!607)
- Remove `rules/gitlab/scala/password/rule-HardcodeKeyEquals.yml` as secret detection should be used instead. (!607)
- Remove `rules/gitlab/scala/password/rule-HardcodeKeySuspiciousName.yml` as secret detection should be used instead. (!607)
- Remove `rules/gitlab/scala/password/rule-HardcodeKeySuspiciousValue.yml` as secret detection should be used instead. (!607)
- Remove `rules/lgpl/javascript/traversal/rule-zip_path_overwrite2.yml` (!588)
- Update `python/sql/rule-hardcoded-sql-expression.yml` (!600)
- Update `rules/lgpl-cc/java/deserialization/rule-InsecureJmsDeserialization.yml` (!581)
- Update `java/crypto/rule-WeakTLSProtocolDefaultHttpClient.yml` (!401)
- Update `rules/lgpl-cc/java/inject/rule-SqlInjection.yml` (!568)
- Update `python/requests/rule-request-without-timeout.yml` (!591)
- Update severity ratings across all Java, Scala, and Kotlin password related rules to match (!607)
- Update `java/password/rule-ConstantDBPassword.yml` to remove patterns that try to match on password like strings (!607)
- Update `rules/lgpl/kotlin/password/rule-HardcodePassword.yml` to remove patterns that try to match on password like strings (!607)
- Update `scala/password/rule-ConstantDBPassword.yml` updated description (!607)
- Update `scala/password/rule-HardcodePassword.yml` updated description (!607)
- Fix test cases for some rules (!627)
- Add missing `metadata.category` for some rules (!628)
- Add missing OWASP 2021 mappings for some rules (!629)

## v2.5.3

- Add `rules/lgpl-cc/java/traversal/rule-RelativePathTraversal` (!489)
- Add `rules/lgpl-cc/java/xxe/rule-DocumentBuilderFactoryDisallowDoctypeDeclMissing` (!511)
- Add `rules/lgpl-cc/java/inject/rule-DangerousGroovyShell` (!566)
- Add `rules/lgpl-cc/java/inject/rule-MongodbNoSQLi.java` (!572)
- Add `rules/gitlab/javascript/crypto/rule-NodeLibcurlSSLVerificationDisable` (!497)
- Add `rules/lgpl-cc/java/crypto/rule-DisallowOldTLSVersion.java` (!539)
- Add `rules/lgpl-cc/java/deserialization/rule-SnakeYamlConstructor.java` (!573)
- Add `rules/lgpl-cc/java/xxe/rule-DisallowDoctypeDeclFalse.java` (!514)
- Add `rules/lgpl-cc/python/flask/security/injection/path-traversal/rule-path-traversal-open` (!536)
- Add `rules/lgpl-cc/java/crypto/rule-UseOfRC4` (!570)
- Add and update missing mappings for rules (!579)
- Add missing mapping for `rules/lgpl-cc/python/flask/security/injection/path-traversal/rule-path-traversal-open` (!599)
- Remove `java/cookie/rule-CookieHTTPOnly` and add `rules/lgpl-cc/java/cookie/rule-CookieHTTPOnly` with enhanced patterns (!439)
- Remove `java/xxe/rule-XMLStreamRdr` and add `rules/lgpl-cc/java/xxe/rule-XMLStreamRdr` with additional patterns (!524)
- Remove `rules/lgpl/javascript/dos/rule-regex_injection_dos` and enhance `javascript/dos/rule-non-literal-regexp` with additional patterns (!512)
- Update `java/file/rule-FilenameUtils` to enhance patterns and use taint mode (!299)
- Update `rules/lgpl/javascript/xml/rule-node_xpath_injection` to reduce false positives (!576)
- Update `java/random/rule-PseudoRandom` and `rules/lgpl/kotlin/random/rule-PseudoRandom` to enhance patterns (!575)
- Update `rules/lgpl/javascript/traversal/rule-generic_path_traversal` to enhance patterns and use taint mode (!553)
- Update `rules/lgpl/javascript/traversal/rule-zip_path_overwrite` to enhance patterns (!580)
- Update `rules/lgpl/javascript/ssrf/rule-node_ssrf` to enhance patterns and use taint mode (!547)
- Update test cases for rule `rules/lgpl/javascript/xml/rule-node_xpath_injection` (!587)

## v2.5.2

- Adjust `rules/python/escaping/rule-jinja2-autoescape-false.yml` because the description field caused an issue with the report ingestion due to a problematic char sequence (!590)

## v2.5.1

- Add `rules/lgpl-cc/java/crypto/rule-SpringHTTPRequestRestTemplate` (!542)
- Add `rules/lgpl-cc/java/deserialization/rule-ServerDangerousObjectDeserialization` (!515)
- Add `rules/lgpl-cc/java/crypto/rule-SpringFTPRequest` (!546)
- Add `rules/lgpl-cc/java/crypto/rule-UseOfRC2` (!557)
- Update `metadata.security-severity` of all rules (!554)
- Update `rules/lgpl/javascript/traversal/rule-express_lfr` to no longer match `baseUrl` (!558)
- Update `rules/lgpl-cc/java/endpoint/rule-ManuallyConstructedURLs.yml` to fix patterns (!556)
- Update `rules/lgpl-cc/python/flask/security/injection/sql/rule-flask-tainted-sql-string.yml` to fix metadata (!562)

## v2.5.0

- Add rules for initial support of Kotlin (!519)
- Add `rules/lgpl-cc/java/csrf/rule-UnrestrictedRequestMapping` Java CSRF Unrestricted Request (!548)
- Add `rules/lgpl-cc/java/crypto/rule-TelnetRequest` Java telnet (!530)
- Add `rules/lgpl-cc/python/pyramid/csrf/rule-pyramid-csrf-origin-check` Python Pyramid CSRF Origin Check Disabled Globally (!516)
- Update `lgpl\javascript\traversal\rule-express-lfr` to enhance source patterns (!551)
- Update `lgpl\javascript\dos\rule-layer7_object_dos` by adding forEach, map, filter, reduceRight and reduce methods as additional sinks (!510)

## v2.4.0

- Add Brakeman rules (!537)
- Add MobSF rules (!518)
- Add `rules/lgpl-cc/java/crypto/rule-HttpGetHTTPRequest` Java HttpGet HTTP request (!535)
- Add `rules/lgpl-cc/java/crypto/rule-HTTPUrlConnectionHTTPRequest` Java HTTPUrlConnection HTTP Request (!533)
- Add `rules/lgpl-cc/java/crypto/rule-SocketRequestUnsafeProtocols` Java Socket Unsafe Protocols (!531)
- Add `rules/lgpl-cc/java/crypto/rule-TLSUnsafeRenegotiation` Java TLS Unsafe Renegotiation (!529)
- Add `rules/lgpl-cc/java/crypto/rule-UnirestHTTPRequest` Java TLS Unirest (!525)
- Add `rules/lgpl-cc/java/file/rule-FilePathTraversalHttpServlet` (!463)
- Add `rules/lgpl-cc/java/xxe/rule-XMLInputFactoryExternalEntitiesEnabled` java xxe xmlinputfactory (!499)
- Update `java/inject/rule-SqlInjection` with missing patterns (!408)
- Update `rules/lgpl-cc/java/inject/rule-SqlInjection` with more sinks, sanitizers and sources (!475)
- Update `python/exec/rule-exec-used` description (!465)
- Update `python/exec/rule-linux-command-wildcard-injection` to cover both wildcards (* and ?) and simplifies the rule (!433)
- Update `rules/lgpl/javascript/jwt/rule-jwt_express_hardcoded` (!455)
- Update `rules/lgpl/javascript/xss/rule-squirrelly_autoescape` to match code written in ES6 (!396)

## v2.3.1

- Add `rules/lgpl-cc/java/endpoint/rule-ManuallyConstructedURLs.yml` to detect unsafely constructed URLs that could lead to SSRF (!363)
- Update `rules/lgpl/javascript/jwt/rule-node_jwt_none_algorithm.yml` to use taint instead of search mode (!448)
- Update `rules/lgpl/javascript/eval/rule-eval_require.js` to use taint instead of search mode (!509)
- Update `rules/lgpl/javascript/crypto/rule-node_sha1.yml` with new patterns for better coverage and with updated metadata (!435)
- Update `rules/lgpl/javascript/ssrf/rule-wkhtmltoimage_ssrf.yml` to use taint instead of search mode (!459)
- Update `rules/lgpl/javascript/traversal/rule-express_lfr.yml` to use taint instead of search mode (!523)

## v2.3.0

- Update C rules for C++ (!532).

## v2.2.0

- Add NodeJS Scan rules (!500)
- Replace `java/xpathi/rule-XpathInjection` with `rules/lgpl-cc/java/xpathi/rule-XpathInjection` to find all cases of insecure xpath functions usage (!488)

## v2.1.3

- Add `rules/lgpl-cc/java/xxe/rule-ExternalGeneralEntitiesTrue` to detect Java XXE External General Entities set to true (!476)
- Add `rules/lgpl-cc/java/xxe/rule-TransformerfactoryDTDNotDisabled` to detect Java XXE Transformerfactory DTD Not disabled (!466)
- Add `rules/lgpl-cc/java/inject/rule-SeamLogInjection` to detect expression execution in Seam logging API (!446)
- Add `rules/lgpl-cc/java/xxe/rule-ExternalParameterEntitiesTrue` to detect Java XXE External Parameter Entities set to True (!469)
- Add `rules/lgpl-cc/javascript/exec/rule-child-process.yml` to detect command injection (!322)
- Add `python/jwt/rule-jwt-none-alg` to detect 'none' algorithm in a JWT token (!470)
- Add `rules/lgpl-cc/java/csrf/rule-SpringCSRFDisabled` to find all cases of disabled CSRF in spring security module (!474)
- Update `rules/lgpl-cc/java/xxe/rule-SAXParserFactoryDisallowDoctypeDeclMissing` with upgraded patterns from community rule (!467)
- Update `rules/lgpl/javascript/crypto/rule-node_tls_reject` to cover more vulnerable cases i.e. reduce false negatives (!449)
- Update `metadata.category` (!487)
- Update `rules/lgpl/javascript/xss/rule-express_xss` to use taint instead of search mode (!414)
- Update `rules/lgpl/javascript/jwt/rule-jwt_exposed_credentials` pattern with regex to match object variables containing the string 'password' (!468)
- Update `rules/lgpl/javascript/xml/rule-node_xpath_injection` by converting it to the taint mode (!501)
- Update `go/crypto/rule-tlsversion` (!504)
- Update `rules/lgpl/javascript/jwt/rule-hardcoded_jwt_secret` (!464)
- Update `go/subproc/rule-subproc.yml` metadata (!517)
- Split WeakHostNameVerification into `java/endpoint/rule-X509TrustManager` and `java/endpoint/rule-HostnameVerifier` (!385)
- Split and update `java/inject/rule-FileDisclosure` into `java/inject/rule-FileDisclosureRequestDispatcher.yml` and `java/inject/rule-FileDisclosureSpringFramework` (!379)
- Remove `javascript/exec/rule-child-process` (!322)
- Remove `rules/lgpl/javascript/dos/rule-express_bodyparser` as vulnerability nolonger exists (!496)
- Remove `rules/lgpl/javascript/crypto/rule-node_curl_ssl_verify_disable` since it's obsolete (!498)
- Remove `rules/lgpl/javascript/xml/rule-xxe_sax` as it's FP prone (!441)

## v2.1.2

- Add `rules/lgpl-cc/java/crypto/rule-GCMNonceReuse.yml` to detect reuse of cryptographic initialization vector (!456)
- Update `go/injection/rule-ssrf.yml` to use taint instead of search mode and add improved patterns and tests (!388)
- Update `rules/lgpl/javascript/xss/rule-handlebars_safestring.yml` to use taint mode, update metadata and add sanitizer patterns and tests (!402)
- Update `go/sql/rule-concat-sqli.yml` to use taint mode to reduce false-positives (!478)
- Remove duplicate rule `rules/lgpl/javascript/exec/rule-generic_os_command_exec.yml` (!477)

## v2.1.1

- Update `rules/lgpl/javascript/crypto/rule-node_insecure_random_generator.yml` with better description text and pattern constraints (!438)
- Update `rules/lgpl/javascript/eval/rule-yaml_deserialize.yml` to match on typescript import pattern (!426)
- Update `rules/lgpl/javascript/xss/rule-handlebars-noescape.yml` with improved patterns and test-cases (!407)
- Update `rules/lgpl/javascript/crypto/rule-node_md5.yml` with improved patterns and description text (!410)
- Update `javascript/xss/rule-mustache-escape.yml` to match on how escape is actually used in mustache (!303)
- Remove `rules/lgpl/javascript/xml/rule-xxe_xml2json.yml` (!440)
- Remove all rules under `rules/lgpl/javascript/generic` as they contain secret detection rules or are FP prone (!437)
- Import initial Ruby ruleset (but not yet enabled) (!430)
- Correctly apply license for `rules/lgpl-cc/java/ftp/rule-FTPInsecureTransport` in distribution file (!447)
- Correctly apply license for `rules/lgpl-cc/java/password/rule-HardcodeKey` in distribution file (!447)
- Correctly apply license for `rules/lgpl-cc/java/crypto/rule-JwtNoneAlgorithm` in distribution file (!447)

## v2.1.0

- Add rules for initial support of PHP (!341)

## v2.0.14

- Add Typescript support to `rules/lgpl/javascript/eval/rule-node_deserialize.yml` (!423)
- Add Typescript support to `rules/lgpl/javascript/eval/rule-serializetojs_deserialize.yml` (!424)
- Update `rules/lgpl-cc/python/django/security/injection/sql/rule-django-rawsql-used` with improved patterns and test-cases (!378)
- Update `rules/lgpl-cc/python/django/security/injection/sql/rule-django-rawsql-used.yml` with improved patterns (!378)
- Remove `java/inject/rule-CustomInjection` as patterns have been merged with `java/inject/rule-SqlInjection` (!409)

## v2.0.13

- Fix `csharp/xss/rule-HtmlElementXss.yml` pattern that was causing false positives (!412)
- Update `rules/lgpl/javascript/eval/rule-grpc_insecure_connection.yml` to support typescript import pattern (!422)

## v2.0.12

- Add `rules/lgpl-cc/java/ftp/rule-FTPInsecureTransport.yml` to test for insecure FTP client usage (!386)
- Add `rules/lgpl-cc/python/django/security/injection/sql/rule-django-raw-used` with improved test-cases (!381)
- Add `rules/lgpl-cc/java/crypto/rule-JwtNoneAlgorithm.yml` to detect JWT none algorithm usage (!353)
- Add `security-severity` metadata fields to all rules to allow for finer grained severity levels (!395)
- Split C# XSS rule into two rules `csharp/xss/rule-HtmlElementXss.yml` and `csharp/xss/rule-ScriptXss.yml` (!310)
- Split C# XXE rule into two rules `csharp/injection/rule-XmlDocumentXXEInjection.yml` and `csharp/injection/rule-XmlReaderXXEInjection.yml` (!367)
- Merge `java/inject/rule-CustomInjectionSQLString.yml` with `java/inject/rule-SqlInjection.yml` (!370)
- Update `java/inject/rule-SqlInjection.yml` to use taint mode (!370)
- Update `csharp/injection/rule-LdapInjection.yml` with additional sinks (!343)
- Update `python/escaping/rule-use-of-mako-templates.yml` to check for use of `default_filters` (!346)
- Update `go/injection/rule-ssrf.yml` to exclude tests (!344)
- Update `go/unsafe/rule-unsafe.yml` to fix description text where sentences were incorrectly duplicated (!376)
- Update `rules/lgpl-cc/java/password/rule-HardcodeKey.yml` with more patterns (!369)
- Update `rules/lgpl-cc/java/password/rule-HardcodeKey.yml` to apply correct license (!369)
- Update `rules/lgpl/javascript/redirect/rule-express_open_redirect.yml` to detect more patterns (!391)
- Update `rules/lgpl/javascript/redirect/rule-express_open_redirect2.yml` to detect more patterns (!398)
- Update `rules/lgpl/javascript/xss/rule-xss_serialize_javascript.yml` with more applicable patterns (!387)
- Update `java/smtp/rule-SmtpClient.yml` with better patterns to reduce false positives (!399)
- Remove `python/exec/rule-import-subprocess.yml` as `import subprocess` does not equate to a vulnerability (!382)
- Remove `go/secrets/rule-secrets.yml` as secret detection should be used for detecting secrets (!205)

## v2.0.11

- License GitLab rules as GitLab Enterprise Edition (!362)
- Update `go/filesystem/rule-decompression-bomb.yml` adds io.LimitReader as a sanitizer (!319)
- Update `java/inject/rule-ELInjection.yml` with additional patterns (!345)
- Add `java/crypto/rule-JwtDecodeWithoutVerify.yml` to detect the decoding of a JWT token without a verify step (!347)
- Add OWASP mappings for all C# rules (!349)
- Add OWASP mappings for all Go rules (!350)
- Add OWASP mappings for all Python rules (!352)
- Add OWASP mappings for all Java rules (!366)
- Remove `java/inject/rule-CLRFInjectionLogs.yml` as modern loggers (from at least 2018) no longer allow injection of control characters (!364)

## v2.0.10

- Update `python/eval/rule-eval.yml` to enhance eval detection, Python constant string parsing and reduce false positives (!307)
- Update `java/endpoint/rule-UnvalidatedRedirect.yml` to use taint analysis mode, add sanitizers and rewrite message (!305)
- Update `python/snmp/rule-snmp_weak_cryptography.yml` to add correct patterns (!311)
- Update `python/urlopen/rule-urllib_urlopen.yml` to reduce false positives and exclude hard-coded strings. (!300)
- Update `java/strings/rule-BadHexConversion.yml` to track taint in loops (!289)
- Update `go/file_permissions/rule-fileperm.yml` with more sensible mask permissions (!318)
- Rename `go/filesystem/rule-filereadtaint.yml` to `go/filesystem/rule-fileread.yml` and convert to taint mode to reduce false positives (!320)
- Rename `go/filesystem/rule-dirtraversal.yml` to `go/filesystem/rule-httprootdir.yml` and use update the CWE from CWE-22 to CWE-552 (!321)
- Update `go/filesystem/rule-tempfiles.yml` with additional patterns (!323)
- Update `go/filesystem/rule-ziparchive.yml` with additional patterns (!325)
- Merge `go/http/rule-slowloris.yml` into `go/http/rule-http-serve.yml` (!332)
- Update `go/leak/rule-pprof-endpoint.yml` with more applicable patterns (!333)
- Remove `go/memory/rule-math-big-rat.yml` this flaw only affects older Go versions (!334)
- Update `go/network/rule-bind-to-all-interfaces.yml` with a better regex to match all bind interfaces (!336)
- Update `csharp/csrf/rule-Csrf.yml` with additional pattern-not constraints to reduce false positives (!285)
- Add and update OWASP 2017 and OWASP 2021 mappings to all C rules (!340)
- Update `java/cookie/rule-HttpResponseSplitting.yml` with fixed regex to match CR LF characters and add more sources (!262)
- Update `java/file/rule-FileUploadFileName.yml` with better description text and improved patterns (!326)
- Rename `python/ssh/rule-ssl-nohost-key-verification.py` to `python/ssh/rule-ssh-nohost-key-verification.py` (!329)
- Update `csharp/password/rule-PasswordComplexity.yml` to match on the correct password setting values (!324)
- Rename `python/urlopen/rule-urllib-urlopen1.yml` to `python/urlopen/rule-urllib-urlopen.yml` and update with additional patterns (!300)

## v2.0.9

- Update `java/cookie/rule-CookieHTTPOnly.yml` to support jakarta servlet (!277)
- Removed `java/xss/rule-XSSReqParamToSendError.yml` as sendError is now automatically encoded and this was a bug (CVE-2008-1232) fixed in Apache Tomcat 6 in 2008 (!276)
- Update `java/cookie/rule-CookieInsecure.yml` to support jakarta servlet (!281)
- Update `java/xss/rule-WicketXSS.yml` to cover more sinks (!284)
- Update `java/script/rule-ScriptInjection.yml` to match invokeFunction() and invokeMethod() with added sinks and rule out false positives for eval() (!266)
- Update `java/xpathi/rule-XpathInjection.yml` to include taint mode analysis and to add sanitizer for setting custom variable resolver (!283)
- Update `csharp/injection/rule-CommandInjection.yml` to ignore hardcoded strings (!286)
- Update `python/deserialization/rule-pickle.yml` to reduce false positives (!288)
- Add back `java/inject/rule-CustomInjectionSQLString.yml` with more strict patterns for matching possible sql injection strings (!298)
- Update `csharp/other/rule-UnsafeXSLTSettingUsed.yml` by changing CWE-611 to 74, update patterns (!291)
- Update `javascript/eval/rule-eval-with-expression.yml` to add more sinks for `eval` style injections (!293)
- Update `java/cookie/rule-RequestParamToHeader.yml` to fix regex match on new lines, add more sinks (!296)
- Update `csharp/injection/rule-CommandInjection.yml` to add more patterns to match command injection (!297)
- Update `csharp/endpoint/rule-UnvalidatedRedirect.yml` to add sources and sinks (!279)
- Update `java/xml/rule-SAMLIgnoreComments.yml` to add fully qualified class name (!287)

## v2.0.8

- Update `go/sql/rule-concat-sqli.yml` to cover more cases and merge it with `go/sql/rule-format-string-sqli.yml` (!272)
- Update `go/injection/rule-ssrf.yml` to remove false-positives (!273)
- Update `python/exec/rule-subprocess-popen-shell-true.yml` to remove false-positives (!274)
- Update `python/sql/rule-hardcoded-sql-expression.yml` to remove false-positives (!278)

## v2.0.7

- Update Java LDAP injection rule (!255)
  - `java/inject/rule-LDAPInjection.yml` - Removed the java.util.Properties.Put() sink
  - `java/inject/rule-LDAPInjection.yml` - To match classes that are not fully qualified in imports
- Update `java/script/rule-SpelExpressionParser.yml` to also match parseRaw() injections (!254)
- Update `java/strings/rule-ModifyAfterValidation.yml` to match `replaceAll`, `replaceFirst` & `concat` as possible sinks (!246)
- Rename `java/script/rule-SpelExpressionParser.yml` to `rule-SpringSpelExpressionParser.yml` to avoid naming collision (!263)
- Update `java/cors/rule-PermissiveCORSInjection.yml` with additional sinks (!264)
- Update the existing rule `rules/lgpl/javascript/database/rule-node_sqli_injection.yml` to add support for sequelize, optimize existing patterns and cover more sql cases. (!261)

## v2.0.6

- Update `java/crypto/rule-RsaNoPadding.yml` to eliminate NoPadding false-positives when RSA is not being used (!249)

## v2.0.5

- Fix typos and language (!238)
  - `c/format/rule-snprintf-vsnprintf.yml` - Expand `$SIZ` pattern variable to `$SIZE`
  - `c/obsolete/rule-gsignal-ssignal.yml` - Use of the American English spelling for 'signaling'
  - `java/cors/rule-PermissiveCORSInjection.yml` - `getParameter` method typo in match pattern
  - `java/inject/rule-SqlInjection.yml` - `update` method typo in match pattern
  - `java/password/rule-HardcodeKeyEquals.yml` - `compare` method typo in match pattern
  - `java/strings/rule-NormalizeAfterValidation.yml` - Typo in description
  - `scala/cors/rule-PermissiveCORSInjection.yml` - `getParameter` method typo in match pattern
  - `scala/inject/rule/SqlInjection.yml` - `update` method typo in match pattern
  - `scala/password/rule-HardcodeKeyEquals.yml` - `compare` method typo in match pattern

## v2.0.4

- Update Go Path Traversal Rule (!235)
  - `go/filesystem/rule-filereadtaint.yml` - Reads via `os.ReadFile` will now be detected as part of CWE-22
  - `go/filesystem/rule-filereadtaint.yml` - Remove `filepath.Rel` from pattern exclusions as it doesn't provide a reliable way to mitigate path traversal

## v2.0.3

- Fix incorrect OWASP Top 10 category references in rules: (!234)
  - `python/escaping/rule-django.yml` - `A7:2017-Cross-Site Scripting (XSS)`
  - `python/exec/rule-start-process-partial-path.yml` - `A1:2017-Injection`
  - `python/exec/rule-start-process-path.yml` - `A1:2017-Injection`
  - `python/exec/rule-subprocess-call-array.yml` - `A1:2017-Injection`

## v2.0.2

- Remove Java Rules (!220)
  - `java/cookie/rule-CookiePersistent.yml` - Cookies may not contain sensitive information and should be removed to be consistent with C# rules
  - `java/cookie/rule-CookieUsage.yml` - Cookies may not contain sensitive information and should be removed to be consistent with C# rules
  - `java/cookie/rule-RequestParamToCookie.yml` - Duplicate rule of `rule-HttpResponseSplitting.yml`
  - `java/cookie/rule-TrustBoundaryViolation.yml` - Unnecessary, prone to false positives
  - `java/cors/rule-PermissiveCORS.yml` - The impact of setting \* in a CORS response is minimal, since credentials will not be sent
  - `java/crypto/rule-DefaultHTTPClient.yml` - While Apache client is deprecated, the default client will connect to a TLS1.3 only server
  - `java/endpoint/rule-UnencryptedSocket.yml` - Using a non-TLS socket is perfectly acceptable in many circumstances
  - `java/endpoint/rule-InsecureServlet.yml` - It's perfectly acceptable to access the data from these methods. Additionally, there is no way a customer could 'fix' this
  - `java/endpoint/rule-JaxRsEndpoint.yml` - Incomplete rule, original [SpotBugs rule](https://find-sec-bugs.github.io/bugs.htm#JAXRS_ENDPOINT) is too broad and prone to false positives
  - `java/endpoint/rule-JaxWsEndpoint.yml` - Incomplete rule, original [SpotBugs rule](https://find-sec-bugs.github.io/bugs.htm#JAXWS_ENDPOINT) is too broad and prone to false positives
  - `java/file/rule-FileUploadFileName.yml` - This is a source not a sink
  - `java/form/rule-FormValidate.yml` - ActionForm/ValidatorForm is from Struts 1.1, which was EoL'd 2013
  - `java/inject/rule-AWSQueryInjection.yml` - SimpleDB, while still technically supported, is deprecated and no longer available to new accounts
  - `java/inject/rule-BeanPropertyInjection.yml` - Apache common collections 3 is no longer available and only works on Java 1.3
  - `java/inject/rule-CustomInjectionSQLString.yml` - Prone to false positives and rules do not necessarily match variables that will be used in a SQL query
  - `java/inject/rule-PathTraversalIn.yml` - Logic handled better by `rule-SpotbugsPathTraversalAbsolute.yml`
  - `java/inject/rule-PathTraversalOut.yml` - Logic handled better by `rule-SpotbugsPathTraversalAbsolute.yml`
  - `java/ldap/rule-EntryPoisoning.yml` - $SCOPE could legitimately have a value, logic handled better by `inject/rule-LDAPInjection`
  - `java/password/rule-HardcodeKeySuspiciousName.yml` - Secrets scanning should be used instead
  - `java/password/rule-HardcodeKeySuspiciousValue.yml` - Secrets scanning should be used instead
  - `java/perm/rule-OverlyPermissiveFilePermissionObj.yml` - Logic handled better by `java/perm/rule-OverlyPermissiveFilePermissionInline.yml`
  - `java/strings/rule-ImproperUnicode.yml` - Code quality issue more than a security issue
  - `java/unsafe/rule-InformationExposure.yml` - Printing stack trace information to the local machine is perfectly acceptable
  - `java/unsafe/rule-InformationExposureVariant2.yml` - Printing stack trace information to the local machine is perfectly acceptable
  - `java/xml/rule-ApacheXmlRpc.yml` - Apache Xml RPC was deprecated in 2013
  - `java/xss/rule-RequestWrapper.yml` - Appears to be a custom rule, `stripXSS()` is not a valid override
  - `java/xss/rule-XSSServlet.yml` - Duplicate of `java/xss/rule-XSSReqParamToServletWriter.yml`
  - `java/xss/rule-XSSServletParameter.yml` This is a source not a sink
  - `java/xxe/rule-XPathXXE.yml` - Rule matches a hardcoded variable name, and has no namespace/import associated with it. Better XXE rule required
  - `java/xxe/rule-Trans.yml` - Duplicate of `java/xml/rule-XsltTransform.yml` with less information

## v2.0.1

- Update JavaScript `rule-non-literal-regexp.yml` to filter out usage of RegExp literals (!233)
- Update JavaScript `rule-non-literal-regexp.yml` to match non-constructor `RegExp()` function calls (!233)
- Remove `c/buffer/rule-getpw.yml` - `getpw` function is deprecated in favor of `getpwuid` since 1979 (!229)
- Remove `c/buffer/rule-equal-mismatch.yml` - Rule is for C++ code (!229)
- Rule bug fixes and improvements (!229)
  - `c/buffer/rule-StrCat-StrCatA.c` - Incorrect letter casing in `strcat` pattern
  - `c/buffer/rule-gets-getts.yml` - Add rule for `_getws` function
  - `c/buffer/rule-sprintf-vsprintf.c` - Add `_T` macro to `_tscanf` function pattern

## v2.0.0

- Switch to package registry for releases (!231)

## v1.3.45

- Remove poor C# rules (!218)
  - `csharp/cache/rule-OutputCacheConflicts.yml` - Unable to confirm vulnerability
  - `csharp/other/rule-AuthorizationBypass.yml` - Highly prone to false positives as it assumes any controller without `[AllowAnonymous]` or `[Authorize]` is an authorization bypass

## v1.3.44

- Remove poor JavaScript rules (!219)
  - `javascript/csrf/rule-no_csrf_before_method_override.yml` - Deprecated and no way of testing, see http://blog.nibblesec.org/2014/05/nodejs-connect-csrf-bypass-abusing.html
  - `javascript/react/rule-missing_noopener.yml` - Browsers no longer allow this by default, see https://gitlab.com/gitlab-org/gitlab/-/issues/233079#note_513860690

## v1.3.43

- Remove poor Python rules (!217)
  - `python/cgi/rule-import_httpoxy.yml` - Not vulnerable since 2016 https://bugs.python.org/issue27568
  - `python/crypto/rule-import_pyghmi.yml` - Old rule from 2013 https://www.cisa.gov/news-events/alerts/2013/07/26/risks-using-intelligent-platform-management-interface-ipmi
  - `python/escaping/rule-mark_safe.yml` - Duplicate of `rule-django.yml`
  - `python/exception/rule-try_except_continue.yml` - Not a security rule
  - `python/exception/rule-try_except_pass.yml` - Not a security rule
  - `python/ftp/rule-import_ftplib.yml` - Duplicate rule, see `rule-ftplib.yml`
  - `python/https/rule-httpsconnection.yml` - Software Composition Analysis (SCA) problem, not a SAST problem (flag if python < 3.4.3 and HTTPSConnection is used)
  - `python/secrets/` - enable secret detection instead
  - `python/telnet/rule-telnetlib.yml` - Duplicate of `rule-import_telnib.yml`
  - `python/tmpdir/rule-specialdir.yml` - It is perfectly fine to use `/dev/shm` as a tmpfs. Rule for using /tmp/ directly is flagged in `rule-hardcodedtmp.yml`
  - `python/tmpdir/rule-tempnam.yml` - `tempnam` was removed in Python 3, Python 2.7 is no longer supported
  - `python/urlopen/rule-urllib_urlopen2.yml` - Duplicate of `rule-urllib_urlopen1.yml` and also missing patterns
  - `python/xml/rule-import_pickle.yml` - Duplicate rule, see `deserialization/rule-pickle.yml`
  - `python/xml/rule-import_...` - Removed all `import` rules as they are just duplicates of the other rules

## v1.3.42

- `csharp/deserialization/rule-InsecureDeserialization.yml` - Convert to taint mode and improve precision to illiminate false-positive (!228)

## v1.3.41

- Remove poor Go rules (!216)
  - `go/audit/rule-unhandled_error.yml` - Empty placeholder rule
  - `go/blocklist/rule-blocklist-cgi.yml` - Only problematic in Go <1.6.3 and we can't currently determine the version
  - `go/crypto/rule-weakcrypto.yml` - Removed in favor of crypto blocklist rules with better descriptions and recommendations

## v1.3.40

- Remove poor or outdated C rules (!215)
  - c/buffer/rule-char_TCHAR.yml - Using character arrays is fine
  - c/buffer/rule-getchar_fgetc.yml - Using getchar does not constitute a vulnerability
  - c/buffer/rule-getopt_getopt_long.yml - This is a bug from 1999, see: https://stackoverflow.com/questions/64305167/flawfinder-error-internal-buffer-overflows-how-to-limit-string-input-size-and
  - c/misc/rule-chroot.yml - Does not point to any specific vulnerability.
  - c/misc/rule-InitializeCriticalSection.yml - This is no longer true since XP / 2003
  - c/race/rule-chgrp.yml - There is no such function (only a unix command line utility)
  - c/input/recv_recvfrom.yml - This is a source not a sink

## v1.3.39

- Revert rule changes made in (!193), (!198), (!199), (!197), (!194), and (!188) to allow for staged release of those MRs (!214)
- Fix `$ADDR` var bind error in `find_sec_bugs_scala.URLCONNECTION_SSRF_FD` scala rule (!214)
- Fix `$PWD` var bind error in `find_sec_bugs.HARD_CODE_PASSWORD` java rule (!214)

## v1.3.38

- Change rule ID format from `find_sec_bugs.XYZ` to `find_sec_bugs_scala.XYZ` for Scala rules (!202)

## v1.3.37

- Disable SAST `message` field wordwrap and update rules that had incorrectly wrapped URLs. (!200)

## v1.3.36

- Remove Java Rules (!193)
  - `java/cookie/rule-CookiePersistent.yml` - Cookies may not contain sensitive information and should be removed to be consistent with C# rules
  - `java/cookie/rule-CookieUsage.yml` - Cookies may not contain sensitive information and should be removed to be consistent with C# rules
  - `java/cookie/rule-RequestParamToCookie.yml` - Duplicate rule of `rule-HttpResponseSplitting.yml`
  - `java/cookie/rule-TrustBoundaryViolation.yml` - Unnecessary, prone to false positives
  - `java/cors/rule-PermissiveCORS.yml` - The impact of setting \* in a CORS response is minimal, since credentials will not be sent
  - `java/crypto/rule-DefaultHTTPClient.yml` - While Apache client is deprecated, the default client will connect to a TLS1.3 only server
  - `java/endpoint/rule-UnencryptedSocket.yml` - Using a non-TLS socket is perfectly acceptable in many circumstances
  - `java/endpoint/rule-InsecureServlet.yml` - It's perfectly acceptable to access the data from these methods. Additionally, there is no way a customer could 'fix' this
  - `java/endpoint/rule-JaxRsEndpoint.yml` - Incomplete rule, original [SpotBugs rule](https://find-sec-bugs.github.io/bugs.htm#JAXRS_ENDPOINT) is too broad and prone to false positives
  - `java/endpoint/rule-JaxWsEndpoint.yml` - Incomplete rule, original [SpotBugs rule](https://find-sec-bugs.github.io/bugs.htm#JAXWS_ENDPOINT) is too broad and prone to false positives
  - `java/file/rule-FileUploadFileName.yml` - This is a source not a sink
  - `java/form/rule-FormValidate.yml` - ActionForm/ValidatorForm is from Struts 1.1, which was EoL'd 2013
  - `java/inject/rule-AWSQueryInjection.yml` - SimpleDB, while still technically supported, is deprecated and no longer available to new accounts
  - `java/inject/rule-BeanPropertyInjection.yml` - Apache common collections 3 is no longer available and only works on Java 1.3
  - `java/inject/rule-CustomInjectionSQLString.yml` - Prone to false positives and rules do not necessarily match variables that will be used in a SQL query
  - `java/inject/rule-PathTraversalIn.yml` - Logic handled better by `rule-SpotbugsPathTraversalAbsolute.yml`
  - `java/inject/rule-PathTraversalOut.yml` - Logic handled better by `rule-SpotbugsPathTraversalAbsolute.yml`
  - `java/ldap/rule-EntryPoisoning.yml` - $SCOPE could legitimately have a value, logic handled better by `inject/rule-LDAPInjection`
  - `java/password/rule-HardcodeKeySuspiciousName.yml` - Secrets scanning should be used instead
  - `java/password/rule-HardcodeKeySuspiciousValue.yml` - Secrets scanning should be used instead
  - `java/perm/rule-OverlyPermissiveFilePermissionObj.yml` - Logic handled better by `java/perm/rule-OverlyPermissiveFilePermissionInline.yml`
  - `java/strings/rule-ImproperUnicode.yml` - Code quality issue more than a security issue
  - `java/unsafe/rule-InformationExposure.yml` - Printing stack trace information to the local machine is perfectly acceptable
  - `java/unsafe/rule-InformationExposureVariant2.yml` - Printing stack trace information to the local machine is perfectly acceptable
  - `java/xml/rule-ApacheXmlRpc.yml` - Apache Xml RPC was deprecated in 2013
  - `java/xss/rule-RequestWrapper.yml` - Appears to be a custom rule, `stripXSS()` is not a valid override
  - `java/xss/rule-XSSServlet.yml` - Duplicate of `java/xss/rule-XSSReqParamToServletWriter.yml`
  - `java/xss/rule-XSSServletParameter.yml` This is a source not a sink
  - `java/xxe/rule-XPathXXE.yml` - Rule matches a hardcoded variable name, and has no namespace/import associated with it. Better XXE rule required
  - `java/xxe/rule-Trans.yml` - Duplicate of `java/xml/rule-XsltTransform.yml` with less information

## v1.3.34

- Remove poor C# rules (!199)
  - `csharp/cache/rule-OutputCacheConflicts.yml` - Unable to confirm vulnerability
  - `csharp/other/rule-AuthorizationBypass.yml` - Highly prone to false positives as it assumes any controller without `[AllowAnonymous]` or `[Authorize]` is an authorization bypass

## v1.3.33

- Remove poor Python rules (!197)
  - `python/cgi/rule-import_httpoxy.yml` - Not vulnerable since 2016 https://bugs.python.org/issue27568
  - `python/crypto/rule-import_pyghmi.yml` - Old rule from 2013 https://www.cisa.gov/news-events/alerts/2013/07/26/risks-using-intelligent-platform-management-interface-ipmi
  - `python/escaping/rule-mark_safe.yml` - Duplicate of `rule-django.yml`
  - `python/exception/rule-try_except_continue.yml` - Not a security rule
  - `python/exception/rule-try_except_pass.yml` - Not a security rule
  - `python/ftp/rule-import_ftplib.yml` - Duplicate rule, see `rule-ftplib.yml`
  - `python/https/rule-httpsconnection.yml` - Software Composition Analysis (SCA) problem, not a SAST problem (flag if python < 3.4.3 and HTTPSConnection is used)
  - `python/secrets/` - enable secret detection instead
  - `python/telnet/rule-telnetlib.yml` - Duplicate of `rule-import_telnib.yml`
  - `python/tmpdir/rule-specialdir.yml` - It is perfectly fine to use `/dev/shm` as a tmpfs. Rule for using /tmp/ directly is flagged in `rule-hardcodedtmp.yml`
  - `python/tmpdir/rule-tempnam.yml` - `tempnam` was removed in Python 3, Python 2.7 is no longer supported
  - `python/urlopen/rule-urllib_urlopen2.yml` - Duplicate of `rule-urllib_urlopen1.yml` and also missing patterns
  - `python/xml/rule-import_pickle.yml` - Duplicate rule, see `deserialization/rule-pickle.yml`
  - `python/xml/rule-import_...` - Removed all `import` rules as they are just duplicates of the other rules

## v1.3.32

- Remove poor Go rules (!194)
  - `go/audit/rule-unhandled_error.yml` - Empty placeholder rule
  - `go/blocklist/rule-blocklist-cgi.yml` - Only problematic in Go <1.6.3 and we can't currently determine the version
  - `go/crypto/rule-weakcrypto.yml` - Removed in favor of crypto blocklist rules with better descriptions and recommendations

## v1.3.31

- Remove poor or outdated C rules (!188)
  - `c/buffer/rule-char_TCHAR.yml` - Using character arrays is fine
  - `c/buffer/rule-getchar_fgetc.yml` - Using getchar does not constitute a vulnerability
  - `c/buffer/rule-getopt_getopt_long.yml` - This is a bug from 1999, see: https://stackoverflow.com/questions/64305167/flawfinder-error-internal-buffer-overflows-how-to-limit-string-input-size-and
  - `c/misc/rule-chroot.yml` - Does not point to any specific vulnerability.
  - `c/misc/rule-InitializeCriticalSection.yml` - This is no longer true since XP / 2003
  - `c/race/rule-chgrp.yml` - There is no such function (only a unix command line utility)
  - `c/input/recv_recvfrom.yml` - This is a source not a sink

## v1.3.30

- Enhance Python ruleset descriptions and titles (!170)

## v1.3.29

- Improve Go memory aliasing in `G601` (!187)

## v1.3.28

- Enhance Javascript ruleset descriptions and titles (!166)

## v1.3.27

- Update Java `rule-SSRF.yml` to match more cases under `java.net.*` package (!186)
- Add Java rule `rule-WeakTLSProtocolVersion.yml` to detect weak TLS versions (!186)

## v1.3.26

- Update Javascript `rule-non_literal_fs_filename.yml` to only flag on fs modules (!183)

## v1.3.25

- Update Java `rule-SpotbugsPathTraversalAbsolute.yml` to handle getResourceAsStream and getResource (!182)

## v1.3.24

- Remove `-1` from all eslint rule IDs (!177)

## v1.3.23

- Update Java `rule-CommandInjection.yml` to match concatenated strings (!169)
- Update Java `rule-SpelView.yml` to also match `ExpressionParser` interface methods (!169)
- Update Java `rule-XpathInjection.yml` to match actual XPath import path (!169)

## v1.3.22

- Update Java `rule-CommandInjection.yml` with ability to match on String arrays (!168)

## v1.3.21

- Update Java `rule-BlowfishKeySize.yml` to add back missing `metavariable` (!169)
- Update Java rules with minor grammatical fixes (!169)

## v1.3.20

- Enhance Java ruleset descriptions and titles (!144)

## v1.3.19

- Update Primary identifiers for `bandit.B303` and `bandit.B304` so that they match the published rules in semgrep (!165)
- Remove `-1` from bandit ruleset IDs and primary identifiers to match the published rules in semgrep (!165)

## v1.3.18

- Update rules that were missing titles by moving them to shortDescription instead of cwe (!161)

## v1.3.17

- Update Primary identifiers for `bandit.B303` and `bandit.B304` so that they match the published rules in semgrep (!155)

## v1.3.16

- Update Primary identifiers for `bandit.B103` so that they match the published rules in semgrep (!154)

## v1.3.15

- Update primary identifier of `bandit.B108-2` to `bandit.B108-1` (!153)

## v1.3.14

- Find Sec Bugs singular rule IDs should include `-1` (!151)
- Security Code Scan singular rule IDs should include `-1` (!151)

## v1.3.13

- feat: Drop high-FP eslint detect-object-injection rule (!150)

## v1.3.12

- Gosec singular rule IDs should include `-1` (!149)

## v1.3.11

- Flawfinder singular rule IDs should include `-1` (!147)

## v1.3.10

- Fix typos in message of yaml load rule (!145)

## v1.3.9

- Enhance usecase coverage for Scala rules (!142)
- Remove redundant mapping of find_sec_bugs in Scala mapping (!142)
- Introduce `native_analyzer` property in the mappings file and use it for primary ID prefix (!142)

## v1.3.8

- Enhance Go ruleset descriptions and titles (!137)

## v1.3.7

- Revert primary identifier changes in !101 to align identifiers to previously-shipped rules (!138)

## v1.3.6

- Update pattern of avoid PyYAML.load in bandit.b506 (!140)

## v1.3.5

- Update C# SQL Injection with link for more details (!139)

## v1.3.4

- Add `generic_error_disclosure` rule for node.js (!124)

## v1.3.3

- Enhance C# ruleset descriptions and titles (!134)

## v1.3.2

- Update `metadata.owasp` to adhere to the pattern `A{number}:{year}-{Title}` (!136)

## v1.3.1

- Enhance C ruleset descriptions and titles (!128)
- Add shortDescription titles to C rulesets (!128)
- Add valdiation to confirm that either cwe tag contains title, or shortDescription is defined (!128)

## v1.3.0

- Add missing OWASP Top10 2017 Categories to C rulesets (!123)
- Fix java/scala OWASP Categories to include missing numerical identifier (!123)
- Add owasp metadata validation to schema (!123)

## v1.2.8

- Improve B608 to work with control flow (!126)

## v1.2.7

- Fix Bandit B113 positional arguments FPs (!122)

## v1.2.6

- Synchronize bandit upstream rules in the ruleset (!119)

## v1.2.5

- Synchronize new upstream rules in the ruleset (!112)

## v1.2.4

- Adjust bandit severity (!116)

## v1.2.3

- Rule refinements for Go (!115)

## v1.2.2

- Rule refinements for Scala (!113)

## v1.2.1

- Support Oracle, Postgres and MySql in .net (community contribution from @masakura) (!107)

## v1.2.0

- Scala support (!109)

## v1.1.12

- Cover more permutations for try...except.. cases (!106)

## v1.1.11

- Eliminate rules that use the `generic` feature (!105)

## v1.1.10

- Fix Bandit B101 rule coverage (!102)

## v1.1.9

- Remove extra colon in bandit rules (!98)

## v1.1.8

- Use single primary id (!101)

## v1.1.7

- Incorporating feedback to improve bandit rule-set (!88)

## v1.1.6

- C# rule refinement (community contribution from @masakura) (!100)

## v1.1.5

- Eliminate FPs for SQLi rule (!95)

## v1.1.4

- Eliminate FPs for SpotBugs hardcoded password rule (!96)

## v1.1.3

- Include eslint security prefix for secondary identifiers only (!95)

## v1.1.2

- Remove security prefix (!94)

## v1.1.1

- Moving the previous id representation; adding more meta information (!93)

## v1.1.0

- Changing deployment target to `/dist`, incorporate meta-information into
  generated rule-packs, update documentation (!87)
