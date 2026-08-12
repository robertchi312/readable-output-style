# Design notes

Every line of the style traces to a named source or a specific failure it fixes. This file is the trace.

## The rules at a glance

| Rule | Comes from | The failure it fixes |
|---|---|---|
| Bottom line first | BLUF, the US Army's correspondence standard (AR 25-50, 1988) | Conclusions buried under topic sentences, so a reader who stops early leaves with nothing |
| Plain words | The plain language movement; Orwell (1946); Pinker's curse of knowledge | Fancy words and undefined terms that slow the reader down until they start skipping |
| Every line earns its place | Grice's maxim of quantity (1975); cognitive load theory | Padding that trains the reader to skim, and compression that makes text denser instead of shorter |
| Never cut a hedge (the fence inside the rule above) | Grice's maxim of quality | Shortening that eats uncertainty markers and leaves replies confidently wrong |
| Bold the load-bearing words | Web reading research (Nielsen, 1997) | Treating skimming as a reader failure instead of designing for it |

## The sources in detail

### Bottom line first

BLUF stands for "bottom line up front". It is the US Army's writing standard from AR 25-50, *Preparing and Managing Correspondence*, published in 1988; the phrase itself entered in the 2001 revision. Its model of the reader: they may stop at any point, so **the decision must sit above the stopping point**. Journalism's inverted pyramid and Barbara Minto's pyramid principle in consulting are the same idea rediscovered in other fields, which is decent evidence the idea is real.

### Plain words

The ordinary word unless a precise term is doing real work, and technical terms defined where they are used. This is the plain language tradition: the Plain English Campaign in the UK since 1979, and in the US the Plain Writing Act of 2010, which made it federal law. Orwell's "Politics and the English Language" (1946) is the ancestor. The define-it-where-you-use-it clause guards against what Steven Pinker calls the curse of knowledge, his diagnosis of why experts write badly: **they cannot imagine not knowing what they know**.

### Every line earns its place

Padding gets cut, and long replies get shorter by dropping topics, never by compressing sentences. The cutting is Grice's maxim of quantity, from "Logic and Conversation" (1975): say as much as needed and no more. The no-compressing half comes from cognitive load theory (John Sweller): compressed text is denser, and **dense text overloads working memory**. Dropping whole topics is the only shortening that actually helps a reader.

One thing is exempt from cutting: hedges. "This works" and "this works but I only tested one case" describe the same work, and the difference between them is everything the reader has when they cannot verify the work themselves. A shortness rule that eats uncertainty markers produces replies that are **confidently wrong**, so the style fences hedges off explicitly. That fence is Grice's maxim of quality: do not assert what you lack evidence for.

### Bold the load-bearing words

Bold marks the decision, the number, or the warning, so that reading only the bold still delivers the true message. This rule accepts that skimming will happen and designs for it instead of against it. Web usability research has said this since Jakob Nielsen's 1997 "How Users Read on the Web" studies: **people scan**, and highlighted keywords measurably improve how much they take in.

## Why the file is 200 words

The built-in styles that ship with Claude Code (Explanatory, Proactive, Learning) run **140 to 450 words**. They are not published anywhere, but their text is readable inside the Claude Code binary with `strings`, and their format set the template here: an identity line, a `# Style Active` marker, and rules written as instructions with a short purpose clause attached ("In order to encourage learning, ...").

The purpose clauses are not decoration. A bare instruction like "bold the necessary words" is ambiguous: necessary for what? The clause "so that reading only the bold still delivers the message" is what defines necessary. Each rule carries exactly what it needs to be unambiguous, a worked example or a single clause, and nothing more.

Anything that traced to no source and changed no output got cut. Active voice, a plain language staple, is absent for exactly that reason: it fixes a problem the replies did not have.

One more habit copied from the built-ins: **strong instructions get fences**. Anthropic's Proactive style spends three rules telling Claude to move fast and two telling it what fast must never mean. The same pattern appears in this style twice, on hedges and on bold ("when everything is bold, nothing is").

## About `keep-coding-instructions`

The frontmatter sets `keep-coding-instructions: true`. Without it, a custom style deletes Claude Code's built-in software engineering guidance (how to scope changes, comment, and verify work) and substitutes its own text. That default exists for styles that turn Claude into something other than a coding assistant. A style that only changes writing should **keep the flag on**. All three built-in styles set it.

## References

- [BLUF (Wikipedia)](https://en.wikipedia.org/wiki/BLUF_(communication)) and [AR 25-50, *Preparing and Managing Correspondence*](https://armypubs.army.mil/), the US Army standard it comes from
- [Grice's cooperative principle and maxims (Wikipedia)](https://en.wikipedia.org/wiki/Cooperative_principle), from "Logic and Conversation" (1975)
- [Plain Writing Act of 2010](https://www.plainlanguage.gov/law/) and the [Plain English Campaign](https://www.plainenglish.co.uk/)
- [Orwell, "Politics and the English Language" (1946)](https://en.wikipedia.org/wiki/Politics_and_the_English_Language)
- [Pinker, *The Sense of Style*](https://en.wikipedia.org/wiki/The_Sense_of_Style), on the curse of knowledge
- [Cognitive load theory (Wikipedia)](https://en.wikipedia.org/wiki/Cognitive_load), from John Sweller's work
- [Nielsen, "How Users Read on the Web" (1997)](https://www.nngroup.com/articles/how-users-read-on-the-web/)
- [Barbara Minto (Wikipedia)](https://en.wikipedia.org/wiki/Barbara_Minto), the pyramid principle
- [Claude Code output styles documentation](https://code.claude.com/docs/en/output-styles)
