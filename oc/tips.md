## Jobs

A job resource represents a one-time task to perform on the cluster. As with most cluster tasks, jobs are executed via pods. If a job's pod fails, then the cluster retries a number of times that the job specifies. The job does not run again after a specified number of successful completions.

Jobs differ from using the kubectl run and oc run commands; both of the latter create only a pod.

Common uses for jobs include the following tasks:

Initializing or migrating a database
Calculating one-off metrics from information within the cluster
Creating or restoring from a data backup
The following example command creates a job that logs the date and time:


## Cron Jobs

A cron job resource builds on a regular job resource by enabling you to specify how often the job should run. Cron jobs are useful for creating periodic and recurring tasks, such as backups or report generation. Cron jobs can also schedule individual tasks for a specific time, such as to schedule a job for a low activity period. Similar to the crontab (cron table) file on a Linux system, the CronJob resource uses the Cron format for scheduling. A CronJob resource creates a job resource based on the configured time zone on the control plane node that runs the cron job controller.

The following example command creates a cron job named date that prints the system date and time every minute:

## Deployments

A deployment creates a replica set to maintain pods. A replica set maintains a specified number of replicas of a pod. Replica sets use selectors, such as a label, to identify pods that are part of the set. Pods are created or removed until the replicas reach the number that the deployment specifies. Replica sets are not managed directly. Instead, deployments indirectly manage replica sets.

Unlike a job, a deployment's pods are re-created after crashing or deletion. The reason is that deployments use replica sets.