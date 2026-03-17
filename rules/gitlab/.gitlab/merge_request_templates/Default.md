## What does this MR do?

<!--
Describe in detail what your merge request does, why it does that, etc.

Please also keep this description up-to-date with any discussion that takes
place so that reviewers can understand your intent. This is especially
important if they didn't participate in the discussion.

Make sure to remove this comment when you are done.
-->

## What are the relevant issue numbers?
<!-- Add links for all issue numbers that are relevant for this merge request. -->

## Does this MR meet the acceptance criteria?

- [ ] The test cases cover both positive and negative cases and have [appropriate Semgrep annotations](https://semgrep.dev/docs/writing-rules/testing-rules/):
  - For positive cases: `// ruleid: ...`
  - For negative cases: `// ok: ....`
- [ ] Prefer `($X.servlet.http.HttpServletResponse $RESP).addCookie($C)` over `$RESPONSE.addCookie($C)` to avoid False-Positives.
- [ ] Following metadata fields exist for the rule(s) added/updated in this MR:
  - `owasp:` with both 2017 and 2021 [mappings](https://owasp.org/www-project-top-ten/assets/images/mapping.png)
  - `shortDescription:` e.g:  `"Use of a broken or risky cryptographic algorithm` *NOT* `"Use of a Broken or Risky Cryptographic Algorithm"`
  - `security-severity:` one of `Info`, `Low`, `Medium`, `High` or `Critical`
  - `pattern:` use multi-line patterns (with `|`) only when the actual search patterns spans more than a single line
- [ ] The message contains a secure code example and no insecure ones.
- [ ] The rule is placed in the correct `rules/` subfolder based on its license, refering to the [internal guidance](https://internal.gitlab.com/handbook/product/sec/secure/sast/rule-licensing/).
- [ ] Relevant labels including workflow labels are appropriately selected.
- [ ] The MR is freshly rebased with `main`.

<!-- Change "type::feature" to "type::maintenance" if you're removing rules or to "type::bug" if you're fixing a bug -->
/label ~"type::feature" ~"devops::secure" ~"section::sec" ~"group::vulnerability research" ~"Category:SAST" ~"SAST::Ruleset"
