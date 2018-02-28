# procfs-test

Testing failing docker-compose build with procfs dependency.

Just run `docker-compose up --build`  inside the repo and it will fail with the following stacktrace:

```
130 user@mac-user ..src/github.com/Nighthawk22/procfs-test % docker-compose up --build                                                                                                      :(
Creating network "procfstest_default" with the default driver
Building web
Traceback (most recent call last):
  File "docker-compose", line 6, in <module>
  File "compose/cli/main.py", line 71, in main
  File "compose/cli/main.py", line 124, in perform_command
  File "compose/cli/main.py", line 1001, in up
  File "compose/cli/main.py", line 997, in up
  File "compose/project.py", line 463, in up
  File "compose/service.py", line 310, in ensure_image_exists
  File "compose/service.py", line 989, in build
  File "site-packages/docker/api/build.py", line 150, in build
  File "site-packages/docker/utils/build.py", line 14, in tar
  File "site-packages/docker/utils/utils.py", line 103, in create_archive
IOError: Can not access file in context: /Users/user/projects/src/github.com/Nighthawk22/procfs-test/vendor/github.com/prometheus/procfs/fixtures/26231/fd/0
Failed to execute script docker-compose
```
