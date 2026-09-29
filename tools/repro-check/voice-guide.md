# Voice guide: how I talk upstream

- A promise that I will fix an issue before I have investigated it.
- A deadline or completion date I cannot guarantee.
- A claim that I reproduced something when my evidence does not show it.
- A guess about the root cause presented as a confirmed fact.
- A generic "same here" or "can confirm" comment without my own reproduction evidence.
- A comment that ignores the repository's required template, contribution rules, or disclosure requirements.
- Dismissive, argumentative, or overly confident language toward maintainers or other contributors.
## Who I am in threads

I am a student contributor learning how to reproduce and document open-source issues carefully. When I comment on an issue, I am reporting what I plan to test or what I directly observed, not presenting myself as a maintainer or expert. Readers can expect specific, evidence-based updates from me without promises I cannot guarantee.

## Rules I write by

### Rule: Say only what I know

I separate what I observed from what I think might be happening. I do not present guesses as confirmed facts.

- Wrong: "This is definitely caused by the parser."
- Right: "I reproduced the reported behavior, but I have not confirmed what is causing it."

### Rule: Be specific about my test

I name the issue behavior or test I am working on instead of posting a generic claim that could apply to any issue.

- Wrong: "I'll take a look at this issue."
- Right: "I'll try to reproduce the reported failure using the setup described in this issue and report what I observe."

### Rule: Do not promise a fix

When claiming an issue, I promise only to investigate and report my results. I do not promise that I will fix the bug or finish by a particular date.

- Wrong: "I'll have this fixed by tomorrow."
- Right: "I'll work through the reproduction steps and post a report with what I find."

### Rule: Let the evidence control the conclusion

My repro comment must describe what actually happened during my test, even when I could not reproduce the issue.

- Wrong: "Confirmed, this bug is reproducible." 
- Right: "I could not reproduce the reported behavior in the environment I tested, so I am reporting the result as cannot-reproduce."

### Rule: Respect the repository's rules

Before posting, I follow any communication, template, or disclosure requirements stated by the repository.

- Wrong: "My comment is good enough even if I skipped the repository's required disclosure."
- Right: "I will include any disclosure or other information required by the repository's contribution policy."
