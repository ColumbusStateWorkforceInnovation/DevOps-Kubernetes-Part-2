# Jobs

## Refresher
[Jobs](https://kubernetes.io/docs/concepts/workloads/controllers/job/) ensure that pods run and successfully terminate. Jobs do one task and can run in parallel. A [CronJob](https://kubernetes.io/docs/concepts/workloads/controllers/cron-jobs/) is a job that runs on a schedule.

## Task 6 (Create a Job)

1. Review the manifest `manifests/job.yml`.
2. Apply the manifest and observe the behavior using `watch kubectl get pods,jobs`. How many jobs run? How many run at the same time? Describe what you observe in the [job_task.md](job_task.md) worksheet.
3. Delete the Job and verify it has been deleted.
4. Update the `manifests/cron.yml` and:
    * set the kind to be `CronJob`
    * use the following `schedule` : "* * * * *"
    * set `successfulJobsHistoryLimit` to 2 and `failedJobsHistoryLimit` to 1
5. Apply the CronJob manifest and immediately run `watch kubectl get pods,cronjobs`. Wait two or three minutes and describe what you observe in the [job_task.md](job_task.md) worksheet.
6. Delete the CronJob and verify it has been deleted.