# Software Ownership at Flow

We build many of our practices at Flow based on the assumption of
strong Software Ownership.

## Litmus test for software ownership

To help us understand what it means for software to be owned, it can
be helpful to enumerate a few litmus tests.

  - Every single line of code is understood and intentional. If
    another team member asks about a particular line of code, the
    owners can explain why they wrote it, what use case they were
    solving and what the pros/cons are that they considered.

  - There are no errors. Period. We've made the decision to not allow
    errors to permeate into our logs. This means that when an error
    does happen, we treat it is a critical Production issue -
    immediately resolving the error condition and then refactoring our
    software to prevent it from occurring in the future. This is hard;
    but by adopting this approach from the beginning we can help avoid
    both errors in production as well as long term 'technical debt'
    from building.

  - When errors occur, we take immediate action. Production errors
    should be fully resolved within 20 minutes in production.

  - Enhancements / additions / changes are easy. With deep
    understanding and ownership of our software, making changes should
    be simple and safe. Should a natural use case arise for a piece of
    software, and we find ourselves reticent to implement - this is a
    sign that our software has missed its mark and should be
    refactored to support natural extension.

## Kaizen - learning from failure

When a failure occurs and after we have restored stability, we take
the time to:

  - Identify other parts of the system with similar characteristics,
    refactoring all software matching the failure pattern before that
    software can fail in the same way.

  - Internalizing the core learnings and incorporating those learnings
    into future software development.

## Production support

In practice, that means we are always on call - if our software
reports an error, it is our responsibility to fix immediately
regardless of time of day.

We like this approach as it creates a strong feedback loop into the
design of the software to prevent future errors, thereby making the
schedule manageable. The end goal is to make failure in production
exceptionally rare.
