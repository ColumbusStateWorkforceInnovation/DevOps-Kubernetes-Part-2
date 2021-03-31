# Jobs

see [here](https://kubernetes.io/docs/concepts/workloads/controllers/job/) for more information on Jobs

### refresher
Jobs ensure that pods run and successfully terminate, where jobs do one task. Acts like an executor with tasks/pods able to be run in parallel.

## Task 6 (Create a Job)

1. Review the manifest `manifests/job.yml`:
2. Apply the manifest and observe the behavior. Observe how many pods are active at one time.
3. Update the `manifests/cron.yml` and make the `Job` above a `CronJob` that runs with the following `schedule` : "*/1 * * * *" and has name `cron-app`
4. set  `successfulJobsHistoryLimit` to 2 and `failedJobsHistoryLimit` to 1
5. Wait and observe what happens, record what you found in the `job_task.md`