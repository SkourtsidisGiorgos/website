---
title: "Dashboard"
subtitle: "The built-in dashboard gives you helpful insights into your background jobs"
date: 2020-04-30T11:12:23+02:00
layout: "documentation"
menu: 
  main: 
    identifier: dashboard
    parent: 'background-methods'
    weight: 1
---
JobRunr includes a built-in dashboard which gives helpful insights into your background job methods. The dashboard allows you to see and control any aspect of background job processing - you have a detailed view on any exception that occurred and you can see the complete background job history.

By default, it is available on the following url: [http://localhost:8000](http://localhost:8000). Of course, this is configurable:

__Using fluent configuration__
<figure>

```java
    JobRunr.configure()
        .useDashboard(8000)
```
<figcaption>The dashboard will be started on port 8000</figcaption>
</figure>

__Using Spring configuration__
<figure>

```java
    @Bean
    public JobRunrDashboardWebServer dashboardWebServer(StorageProvider storageProvider, JsonMapper jsonMapper, int port) {
        final JobRunrDashboardWebServer jobRunrDashboardWebServer = new JobRunrDashboardWebServer(storageProvider, jsonMapper, port);
        jobRunrDashboardWebServer.start();
        return jobRunrDashboardWebServer;
    }
```
<figcaption>The dashboard will be started on the given port which can be provided by an environment variable or a property file.</figcaption>
</figure>


## Screenshots
<figure>
<img src="/documentation/jobrunr-overview-1.webp" class="kg-image">
<figcaption>A complete overview of the amount of jobs that are being processed</figcaption>
</figure>

<figure>
<img src="/documentation/jobs-enqueued.webp" class="kg-image">
<figcaption>An overview of all enqueued jobs</figcaption>
</figure>

<figure>
<img src="/documentation/job-details-failed-2.webp" class="kg-image">
<figcaption>When a job failed, you see a detailed message why it did fail</figcaption>
</figure>

<figure>
<img src="/documentation/job-details-succeeded.webp" class="kg-image">
<figcaption>A detailed overview of a succeeded job</figcaption>
</figure>

<figure>
<img src="/documentation/recurring-jobs-1.webp" class="kg-image">
<figcaption>
An overview of all recurring jobs with the ability to trigger or delete them</figcaption>
</figure>

<figure>
<img src="/documentation/job-servers.webp" class="kg-image">
<figcaption>An overview of all background job servers processing background jobs</figcaption>
</figure>

## JobRunr pro comes with handy dashboard improvements

<figure>
<img src="/documentation/jobrunr-pro-enqueued.webp" class="kg-image">
<figcaption>Thanks to queues, we have an overview how many jobs are enqueued on the high-prio queue, standard queue and low-prio queue</figcaption>
</figure>

<figure>
<img src="/documentation/jobrunr-pro-batches.webp" class="kg-image">
<figcaption>The Pro version also gives an overview of all your batches</figcaption>
</figure>

<figure>
<img src="/documentation/jobrunr-pro-batch-details.webp" class="kg-image">
<figcaption>Follow up on your batch jobs thanks to the enhanced job details of a batch job</figcaption>
</figure>