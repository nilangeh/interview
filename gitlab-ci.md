- Gitlab registry: Private reg for Docker images
- Gitlab caching: Cache is a set of files that a job can download before the execution and upload after completion. The default location of the cache is the home directory of the GitLab Runner. If the distributed cache is configured, S3 works as storage. After execution, it will upload the cache back to the S3 bucket (push).
- Docker layer caching (DLC): Create reusable images that do not change each time they are run, helps reduce the time it takes to run your containers by keeping track of changes to images so that they do not have to be rebuilt every time you upgrade your container.
- Dependency proxy: GitLab provides a local cache called the Dependency Proxy for frequently-accessed upstream images. The Dependency Proxy can act as a pull-through cache in the case of CI/CD by receiving a request from your build server and returning the requested image from the registry.
- Cache dependency: Cache dependencies enable the system to expire cached items when related objects are modified automatically. The system uses dummy cache keys, or cache items with no data that represent one or more other objects, to create dependencies between cached data and other objects.
- Gitlab CI artifacts: Stored in /home/git/gitlab/shared/artifacts by default. In order to keep them backed up regularly, you should save the file and restart GitLab.
- Artifacts: In GitLab 12.4, files and directories from internal and private projects can be previewed when access control is enabled using GitLab Pages. Jobs can output an archive of all the files and directories that are generated as part of the job run in a .zip file. This output is known as a job artifact, which can be downloaded using the GitLab UI or API.
- Variables: GitLab variables can be used to pre-define the values. Go to your project page, Settings tab -> CI/CD, find Variables and click on the Expand button. Here you can define variable names and values, which will be automatically passed into the GitLab pipelines, and are available as environment variables there.
- Gitlab runner: A runner is a lightweight, highly-scalable agent that picks up a CI job through the coordinator API of GitLab CI/CD, runs the job, and sends the result back to the GitLab instance. https://docs.gitlab.com/ee/ci/runners/README.html