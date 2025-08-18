# QA duty

In the Mender team, we have a weekly rotating responsibility for QA, known as "QA duty".
This is a person in the team responsible for:

* Monotiring the health of the Build System
* Doing early investigation on issues
* Report problems to the team

## Mender QA rotation calendar

Link: https://calendar.google.com/calendar/embed?src=northern.tech_m6aop2it00n2jnpiut2j40n39k%40group.calendar.google.com&ctz=Europe%2FOslo

This is the Google calendar that shows who takes this role when.

## Responsibilities

### Overview of unstable tests

Link: https://qastatus.mender.io/stats

The unstable tests should be known to the person on QA duty so that it can be detected when
test failures are genuine or spurious.

By the end of the QA duty period, all failed tests in nightly builds (link above)
should either be fixed or reported in JIRA tasks to follow-up in the next period.

### Nightly Mender QA build (client only)

Link: https://qastatus.mender.io/nightlies

Link: https://gitlab.com/Northern.tech/Mender/mender-qa/-/pipelines?page=1&scope=all&source=schedule

There is no golden rule on what to do when the "Last Pipeline" in the link above
is not green.

The general advise is to do a short investigation before asking for help from
others in the team. For obvious test infra errors we can just re-run the jobs;
for actual test failures we need to asses if it might be a regression or not.

### Nightly Mender Server

Link: https://gitlab.com/Northern.tech/Mender/mender-server/-/pipelines?page=1&scope=all&source=schedule

Link: https://gitlab.com/Northern.tech/Mender/mender-server-enterprise/-/pipelines?page=1&scope=all&source=schedule

Nightly tests over the mender-server monorepo. These include the whole spectrum from unit tests to E2E tests.

The second pipeline is for the Enterprise version but essentially features the same jobs.

### Nightly Mender Server Integration tests

Link: *qastatus link pending*

Link: https://gitlab.com/Northern.tech/Mender/integration/-/pipelines?page=1&scope=all&source=schedule

These tests are related to the Mender Server monorepo artifacts from `main`,
tesing it over the current Mender client artifacts `master`.

There is no golden rule on what to do when the "Last Pipeline" in the link above
is not green.

The general advise is to do a short investigation before asking for help from
others in the team. For obvious test infra errors we can just re-run the jobs;
for actual test failures we need to asses if it might be a regression or not.

### Nightly Mender Gateway

Link: https://gitlab.com/Northern.tech/Mender/mender-gateway/-/pipelines?page=1&scope=all&source=schedule

Nightly pipelines for `mender-gateway`. There are two branches to check: `master` and `2.0.x`

### Weekly Mender integration tests on staging

Link: https://gitlab.com/Northern.tech/Mender/integration/-/pipelines?page=1&scope=all&source=schedule

Every Monday evening, at 9 PM UTC, we run the Mender integration tests targeting
the Mender staging environment.

On Tuesday morning, the person on QA duty must check the status of the pipeline and
do a short investigation before asking for help from others in the team in
case of failures.

### Other notable weekly pipelines

Link: https://gitlab.com/Northern.tech/Mender/integration-test-runner/-/pipeline_schedules

Link: https://gitlab.com/Northern.tech/Mender/mender-mcu/-/pipeline_schedules

Link: https://gitlab.com/Northern.tech/Mender/monitor-client/-/pipeline_schedules

### Individual pipelines

Link: https://qastatus.mender.io/build-status

All should be green. If a pipeline is broken, ping the corresponding team.

Note that `integration staging` is currently broken, you can skip that one.

They get build after every merge to master on the corresponding repository, and
on weekly basis every Tuesday evening, at 9 PM UTC.

### More information

More information about roles and responsibilities can be found in the internal document:

https://docs.google.com/document/d/1pFJbGVM248UoynsMbNox47whrzIfVUrK4hO_xiIWHzA/edit
