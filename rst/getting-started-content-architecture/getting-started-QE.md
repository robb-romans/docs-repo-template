##Content architecture check

**Getting Started navigation**
  - [ ]  Link at top of doc
  - [ ]  GS title in left navigation
  - [ ]  Content hierarchy for top-sections looks like one of these two models.

General API section
- [ ] Authentication section contains short section referencing GS auth example and Identity doc.
- [ ] Service access endpoints topic follows authentication
- [ ] Service access endpoints topic has link to auth response in Review Auth response section.
- [ ] How to use cURL topic not included in the doc

##Content check

**Use cases and examples**

- [ ] Compare use case (topics) in migrated content to original content on docs.rackspace.com to identify any missing content

**Getting Started common content**

- [ ]  Brief intro topic that follows boiler plate, might have extra content depending on product.
- [ ]  Uses common Get Credentials topic ==> Save your API Key, Save your Account number
- [ ]  Send API requests content follows template (some docs have only cURL, some have cURL and CLI)
- [ ]  Authenticate uses common content (H1) and H2 -- Using cURL, and Using client, if both cURL and client. If only cURL, toc has Send ..., Review ..., Configure ... headings.

General API section
- [ ] Authentication section contains short section referencing GS auth example and Identity doc.
- [ ] Service access endpoints topic follows authentication
- [ ] Service access endpoints topic has link to auth response in Review Auth response section.
- [ ] How to use cURL topic not included in the doc

##Copy check

**Check links**
- [ ] Run link check on page.
- [ ] Look for malformed internal and external cross-references
- [ ] Look for link references that aren't linked, or links that refer to html topics from docs.rackspace.com
- [ ] Look for missing punctuation when link is at end of sentence.  
          (You need to leave a space between the end of link and the punctuation. ```This is a :ref:`test <refid>` .```

**Code samples**
- [ ] Make sure spacing is OK -- as good as it can be.
- [ ] Examples use environment variables -- $ENDPOINT, $TENANT_ID, and $AUTH_TOKEN  (just mark it if not used, not critical but prefereable.)
- [ ] Paragraph text not merged into code samples.

**Inline markup**
- [ ] Look for stray ` or * symbols or funny spacing
- [ ] Find Bold, italic, or inline literal rendering issues
- [ ] Look for stray | or html leftovers  (margin: 0 ... )

**Tables**
- [ ] Check formatting and inline markup for weird stuff
- [ ] Tables have titles 

**Lists**
- [ ] Look for strange indenting or bolding (ragged margins make Sphinx think things are dl lists.)
