A little bit of context here. This was grabbed from an agent that was ready to use spec kit and I responded with this instead. 



 I think there's a step before this which is go and see if there is something else like this already out
there. And that means be able to describe it well enough to be able to search for it properly which means breaking it
into modules that are commonly used in all sorts of things and then you know breaking then thinking about how that
gets glued together into a level above that and what you would call it and then deciding and then doing and then
talking to an agent about how to describe the project in common terms by coming up with this mapping of syntactical
similarities that could help in doing a search and then somehow crawling github and that's a tricky part because I
think githubs like I found more stuff party sites where they show off what's on github you know they highlight stuff
and they make a business out of basically pulling up the interesting stuff and those indexes of github stuff happen to
 be easier to crawl than github is for some reason maybe I don't have the right understanding of how to search through
 github so there's that whole stage of like how do you find this source code and then you want to be able to go to
another step which is testing it and playing with it and seeing how close it is to the thing that you wanted to build
and then you can so that's like I have a prototype it's not prototyping it's a benchmarking or benching or I don't
know when you when you bring a bunch of stuff in and plug it all in and see how it works and see if it works well and
then you make a sort of audit of all of the different projects and things that you've tested to see if there's like a
perfect match a close match or a couple things together solve the problem so you start with that kind of logic where
you see what's out there in the world and then you then it's time to do the next step which is the preparation for
creating a spec because at that point you either know you're going to use something else and you don't have any work
to do because it's all been programmed or that you're going to be plugging in a bunch of programmable parts and the
job is really finding a way to plug them all in together and get them all running on the same system or you're going
to be um doing some variation of that where you're writing chunks of it yourself because it doesn't exist or taking
smaller modules or tiny little bits of source code to fill in some of the gaps or you're all the way at the other end
where you're writing it from scratch which is essentially what we're about to do where we're giving it a spec and what
 I'm starting to think incidentally is when you feed into spec kit what you really want is a functional spec which is
everything you want it to do, all the edge cases and things that it needs to do, and all the things that shouldn't do
as well, so you don't, so that it doesn't get distracted with ideas and things that you're maybe even typically done
that are taking away from the timeline of getting it done immediately that critical path and once you've identified
the critical path that becomes the guiding details for the functional spec MVP and then you have a list of things that
 are outside of the MVP of the functional spec and those get added but they're clearly demarked as phase two or and
and above so phase two being the things you really wanted it to have and phase three being the things that that would
be great to have but aren't important to the functionality of the thing you're building and then that becomes this
sort of functional spec you hand that off to the spec kit it creates the PRD and goes through its pipeline of stuff
you then have some you have a way to then review like it has spec kit has a bunch of built-in things for analyzing
what it builds and the before it actually starts creating the tasks and doing the work you actually can review it and
that should be reviewed against the wealth of information and so what we want to do is understand with that library or
 that bundle of content or details about the project that if you could point if you could ask it the right questions
you could give it you could review what spec kit produces and compare it to your knowledge fault or document
collection or library of content details I don't know what to call it and it would all be there for and with detailed
answers so you'd end up with a cleanup phase that went directly into a very precise PRD and you could then hit run and
 basically get what you wanted out of it.  ultrathink

⏺ Ultrathinking...

  You've identified a critical missing phase in the current workflow. Let me map this out:

  The Complete Software Development Pipeline (As It Should Be)

  Phase 0: Discovery & Validation (CURRENTLY MISSING)

  Problem Statement
      ↓
  Modular Decomposition (break into common patterns)
      ↓
  Taxonomy Mapping (translate to searchable terms)
      ↓
  Search Strategy (GitHub + third-party indexes)
      ↓
  Benchmarking/Testing (actually try candidates)
      ↓
  Audit Matrix (perfect/close/partial/none)
      ↓
  Decision: Use/Integrate/Augment/Build

  Phase 1: Functional Spec (if building/augmenting)

  Complete Functional Requirements
      ↓
  Critical Path Identification
      ↓
  Phase Categorization (MVP/Phase2/Phase3)
      ↓
  Edge Cases & Constraints
      ↓
  Anti-Requirements (what NOT to do)

  Phase 2: Spec-Kit Pipeline (current plan)

  Functional Spec → Spec-Kit
      ↓
  PRD Generation
      ↓
  Review against Knowledge Vault
      ↓
  Cleanup/Refinement
      ↓
  /plan → /tasks → /implement
