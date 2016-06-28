# Contribution Guidelines

Changes are contributed via Pull Requests in github.

Repository maintainers use LGTM (Looks Good To Me) in comments on the code
review to indicate acceptance.

The only hard rules we have:

  - Only the author can merge their pull request. We do this as only
    the author truly knows if a pull request is ready. In addition,
    with continuous delivery, a merge is indicative of code going to
    production. We want the author to be aware of the release of
    their code.

  - A given repository may provide its own contribution guidelines by
    including a Contributing.md in its root repository.

  - If a repository defines an artifact or definition of some sort
    that is itself used in other applications:

      - we require feedback from at least 3 of the dependent owners
        prior to merging (or all of the dependent owners if there are
        fewer than 3). The goals here are to a: minimize surprise by
        people dependent on a chance; b: minimize the number of
        changes in both short term and long term in shared artifacts
        as the cost long term of mistakes here is high.

      - Otherwise, a change requires at least one LGTM from an active
        contributor to the project. For now, this is a loose
        definition given we all know who works on what. Over time, if
        identification of "active contributor" becomes a challenge, we
        will formalize in some way. Note that this means an active
        contributor can immediately merge their own pull request if
        they so choose, or can otherwise highlight a PR for which they
        would like review / suggestions. Note that even in the case of
        immediate merge, the primary value of the pull request is
        notifciation to the rest of the team.

  - If a repository is Top Secret, a change requires at least one LGTM
    from at least one other employee with Top Secret clearance.


## Making changes to standards

Changes to the standards repository follow our standard [contribution guidelines](Contributing.md). The only active contributor to this project is Michael Bryzek.
