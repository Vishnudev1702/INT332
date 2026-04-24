(base) vishnudevsakthivel@Vishnudevs-MacBook-Air ~ % cd ~/docker-maven-demo
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % mkdir -p .github/workflows
touch .github/workflows/ci.yml
open -e .github/workflows/ci.yml
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % git add .                                                   
git commit -m "Practical 4: Java CI with Maven"
git push
[main af0e344] Practical 4: Java CI with Maven
 1 file changed, 31 insertions(+)
 create mode 100644 .github/workflows/ci.yml
To https://github.com/Vishnudev1702/INT332.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/Vishnudev1702/INT332.git'
hint: Updates were rejected because the remote contains work that you do not
hint: have locally. This is usually caused by another repository pushing to
hint: the same ref. If you want to integrate the remote changes, use
hint: 'git pull' before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % git pull origin main --no-rebase
remote: Enumerating objects: 32, done.
remote: Counting objects: 100% (32/32), done.
remote: Compressing objects: 100% (17/17), done.
remote: Total 30 (delta 12), reused 25 (delta 7), pack-reused 0 (from 0)
Unpacking objects: 100% (30/30), 6.49 KiB | 229.00 KiB/s, done.
From https://github.com/Vishnudev1702/INT332
 * branch            main       -> FETCH_HEAD
   a08ac1b..068777f  main       -> origin/main
Merge made by the 'ort' strategy.
 .github/workflows/ci-cd.yml               |  23 +++++++++
 .gitignore                                |  15 ++++++
 22-04-2026.md                             | 203 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 23-04-2026.md                             |  93 ++++++++++++++++++++++++++++++++++++
 Dockerfile                                |   7 +--
 app.py                                    |   9 ++++
 my-docker-app/.github/workflows/ci-cd.yml |  20 ++++++++
 my-docker-app/.gitignore                  |  15 ++++++
 my-docker-app/22-04-2026.md               | 203 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 my-docker-app/Dockerfile                  |   5 ++
 my-docker-app/app.py                      |   9 ++++
 my-docker-app/requirements.txt            |   1 +
 requirements.txt                          |   1 +
 13 files changed, 601 insertions(+), 3 deletions(-)
 create mode 100644 .github/workflows/ci-cd.yml
 create mode 100644 .gitignore
 create mode 100644 22-04-2026.md
 create mode 100644 23-04-2026.md
 create mode 100644 app.py
 create mode 100644 my-docker-app/.github/workflows/ci-cd.yml
 create mode 100644 my-docker-app/.gitignore
 create mode 100644 my-docker-app/22-04-2026.md
 create mode 100644 my-docker-app/Dockerfile
 create mode 100644 my-docker-app/app.py
 create mode 100644 my-docker-app/requirements.txt
 create mode 100644 requirements.txt
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % git push
Enumerating objects: 13, done.
Counting objects: 100% (13/13), done.
Delta compression using up to 8 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (9/9), 1.05 KiB | 1.05 MiB/s, done.
Total 9 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/Vishnudev1702/INT332.git
   068777f..120ac1f  main -> main
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % open -e .github/workflows/ci.yml
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % open -e Dockerfile
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % mvn clean package
docker build -t java-app .
WARNING: A terminally deprecated method in sun.misc.Unsafe has been called
WARNING: sun.misc.Unsafe::staticFieldBase has been called by com.google.inject.internal.aop.HiddenClassDefiner (file:/opt/homebrew/Cellar/maven/3.9.11/libexec/lib/guice-5.1.0-classes.jar)
WARNING: Please consider reporting this to the maintainers of class com.google.inject.internal.aop.HiddenClassDefiner
WARNING: sun.misc.Unsafe::staticFieldBase will be removed in a future release
[INFO] Scanning for projects...
[INFO] 
[INFO] -------------------< com.example:docker-maven-demo >--------------------
[INFO] Building docker-maven-demo 1.0-SNAPSHOT
[INFO]   from pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- clean:3.2.0:clean (default-clean) @ docker-maven-demo ---
[INFO] Deleting /Users/vishnudevsakthivel/docker-maven-demo/target
[INFO] 
[INFO] --- resources:3.3.1:resources (default-resources) @ docker-maven-demo ---
[WARNING] Using platform encoding (UTF-8 actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] skip non existing resourceDirectory /Users/vishnudevsakthivel/docker-maven-demo/src/main/resources
[INFO] 
[INFO] --- compiler:3.13.0:compile (default-compile) @ docker-maven-demo ---
[INFO] Recompiling the module because of changed source code.
[WARNING] File encoding has not been set, using platform encoding UTF-8, i.e. build is platform dependent!
[INFO] Compiling 1 source file with javac [debug target 17] to target/classes
[WARNING] location of system modules is not set in conjunction with -source 17
  not setting the location of system modules may lead to class files that cannot run on JDK 17
    --release 17 is recommended instead of -source 17 -target 17 because it sets the location of system modules automatically
[INFO] 
[INFO] --- resources:3.3.1:testResources (default-testResources) @ docker-maven-demo ---
[WARNING] Using platform encoding (UTF-8 actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] skip non existing resourceDirectory /Users/vishnudevsakthivel/docker-maven-demo/src/test/resources
[INFO] 
[INFO] --- compiler:3.13.0:testCompile (default-testCompile) @ docker-maven-demo ---
[INFO] Recompiling the module because of changed dependency.
[WARNING] File encoding has not been set, using platform encoding UTF-8, i.e. build is platform dependent!
[INFO] Compiling 1 source file with javac [debug target 17] to target/test-classes
[WARNING] location of system modules is not set in conjunction with -source 17
  not setting the location of system modules may lead to class files that cannot run on JDK 17
    --release 17 is recommended instead of -source 17 -target 17 because it sets the location of system modules automatically
[INFO] 
[INFO] --- surefire:3.2.5:test (default-test) @ docker-maven-demo ---
[INFO] Using auto detected provider org.apache.maven.surefire.junit4.JUnit4Provider
[INFO] 
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running com.example.AppTest
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.015 s -- in com.example.AppTest
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] 
[INFO] --- jar:3.3.0:jar (default-jar) @ docker-maven-demo ---
[INFO] Building jar: /Users/vishnudevsakthivel/docker-maven-demo/target/docker-maven-demo-1.0-SNAPSHOT.jar
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  1.162 s
[INFO] Finished at: 2026-04-24T12:20:35+05:30
[INFO] ------------------------------------------------------------------------
[+] Building 25.9s (9/9) FINISHED                                                                           docker:desktop-linux
 => [internal] load build definition from Dockerfile                                                                        0.0s
 => => transferring dockerfile: 140B                                                                                        0.0s
 => [internal] load metadata for docker.io/library/eclipse-temurin:21-jdk                                                   3.9s
 => [auth] library/eclipse-temurin:pull token for registry-1.docker.io                                                      0.0s
 => [internal] load .dockerignore                                                                                           0.0s
 => => transferring context: 2B                                                                                             0.0s
 => [1/3] FROM docker.io/library/eclipse-temurin:21-jdk@sha256:e58e492628c1428ceb838afc1a1b8762673d5eaa09296f560c363daea0  21.1s
 => => resolve docker.io/library/eclipse-temurin:21-jdk@sha256:e58e492628c1428ceb838afc1a1b8762673d5eaa09296f560c363daea0f  0.0s
 => => sha256:ff2edbdda742b8209749da8312055504fd22ba27cf54ff90a8df515ef801f217 2.28kB / 2.28kB                              0.8s
 => => sha256:ab3882fc557dcd485fbffc75ce883a4caf98ff249556fe7ff1f9912a8a854caa 160B / 160B                                  1.1s
 => => sha256:d28e9fa98f33516820c63a2c5e371c9b4a59055d805992c5a5b5a827e7bc58aa 156.14MB / 156.14MB                         20.1s
 => => sha256:018756a5babae49a61cd59845b003384d7232846dde43abdc0a2a782f626c4a8 24.17MB / 24.17MB                            7.7s
 => => sha256:818154cda96df8bbb276b4f4339124da55756620a1037af15570bc95312850fa 28.88MB / 28.88MB                            7.6s
 => => extracting sha256:818154cda96df8bbb276b4f4339124da55756620a1037af15570bc95312850fa                                   0.4s
 => => extracting sha256:018756a5babae49a61cd59845b003384d7232846dde43abdc0a2a782f626c4a8                                   0.3s
 => => extracting sha256:d28e9fa98f33516820c63a2c5e371c9b4a59055d805992c5a5b5a827e7bc58aa                                   1.0s
 => => extracting sha256:ab3882fc557dcd485fbffc75ce883a4caf98ff249556fe7ff1f9912a8a854caa                                   0.0s
 => => extracting sha256:ff2edbdda742b8209749da8312055504fd22ba27cf54ff90a8df515ef801f217                                   0.0s
 => [internal] load build context                                                                                           0.0s
 => => transferring context: 2.50kB                                                                                         0.0s
 => [2/3] WORKDIR /app                                                                                                      0.8s
 => [3/3] COPY target/*.jar app.jar                                                                                         0.0s
 => exporting to image                                                                                                      0.1s
 => => exporting layers                                                                                                     0.0s
 => => exporting manifest sha256:a1056dded3c01f767d8907df0880a7924a28470a52f3fa515ed159374d64660f                           0.0s
 => => exporting config sha256:65f61a712c950ce5ad0dc7f2b0db12674fb1ce4357fd784e70096031257abf6b                             0.0s
 => => exporting attestation manifest sha256:9ecd5abe19f39309d20f0c7db8fc3833d91bedb1c6a10e7a4ee605177430db59               0.0s
 => => exporting manifest list sha256:1e3531dafeaaf0ab63bbf5003ace5f4d565eb1541c860e68ca35345b0e7b996c                      0.0s
 => => naming to docker.io/library/java-app:latest                                                                          0.0s
 => => unpacking to docker.io/library/java-app:latest                                                                       0.0s

View build details: docker-desktop://dashboard/build/desktop-linux/desktop-linux/034wjnmepokpw5tgd5qj935mn
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % docker run -d --name java-container java-app
2076dd65643a1febdf2890764266d98f5efde00a794902e304e209a08eb5d002
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % docker ps
CONTAINER ID   IMAGE       COMMAND                  CREATED       STATUS         PORTS                 NAMES
2807d2ecff6f   mysql:8.0   "docker-entrypoint.s…"   2 weeks ago   Up 9 minutes   3306/tcp, 33060/tcp   mysql-db
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % cd ~/docker-maven-demo
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % touch 24-04-2026.md
open -e 24-04-2026.md
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % git add .
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % git commit -m "Daily practice: Java CI with Maven (24-04-2026)"
[main 4648408] Daily practice: Java CI with Maven (24-04-2026)
 17 files changed, 287 insertions(+), 17 deletions(-)
 create mode 100644 24-04-2026.md
 delete mode 100644 target/jib-cache/jib-classpath-file
 delete mode 100644 target/jib-cache/jib-main-class-file
 delete mode 100644 target/jib-cache/layers/44aad9f6c62c31fc054b5fc41e51e987d47f5fbdb629731ae2ac9c1bfe94b783/e9bfe7616a0968896b94354b8d745b537bbe0bfd8207e0ce001f6ebe98a8ad79
 delete mode 100644 target/jib-cache/layers/8bb1ae3ec8cd82153c775b78682d4a87757d4a3aaa540f02117b4e480be40f77/961ecf2529045ceb76a3d6c3804f013253e75bc52518eb7ecfea2cecfd9e81f1
 delete mode 100644 target/jib-cache/layers/dca0b326bbcd818ee6765cc6d579f8a8feef0dc5a37dd707fb9d787c25d3df1c/06aafb0ebbf160da94a24d15b2ff17f284128f6abed7f9f841c9bd67958379a7
 delete mode 100644 target/jib-cache/selectors/24dbefd30cb78b8246ff140875dd809ccde60dca0c3f30b7d2bd83304c0c896b
 delete mode 100644 target/jib-cache/selectors/b1c25647165556977b716abd04511ec94b6322166d09abbb2dbe4f9afe4ec380
 delete mode 100644 target/jib-cache/selectors/fe01e8ab2332970479a8a7a3cf30bab9abf80b15ba5677ed7f414ae450cb9fc9
 delete mode 100644 target/jib-image.digest
 delete mode 100644 target/jib-image.id
 delete mode 100644 target/jib-image.json
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % git pull origin main --no-rebase -m "merge"
error: unknown switch `m'
usage: git pull [<options>] [<repository> [<refspec>...]]

    -v, --[no-]verbose    be more verbose
    -q, --[no-]quiet      be more quiet
    --[no-]progress       force progress reporting
    --[no-]recurse-submodules[=<on-demand>]
                          control for recursive fetching of submodules

Options related to merging
    -r, --[no-]rebase[=(false|true|merges|interactive)]
                          incorporate changes by rebasing rather than merging
    -n                    do not show a diffstat at the end of the merge
    --[no-]stat           show a diffstat at the end of the merge
    --[no-]log[=<n>]      add (at most <n>) entries from shortlog to merge commit message
    --[no-]signoff[=...]  add a Signed-off-by trailer
    --[no-]squash         create a single commit instead of doing a merge
    --[no-]commit         perform a commit if the merge succeeds (default)
    --[no-]edit           edit message before committing
    --[no-]cleanup <mode> how to strip spaces and #comments from message
    --[no-]ff             allow fast-forward
    --ff-only             abort if fast-forward is not possible
    --[no-]verify         control use of pre-merge-commit and commit-msg hooks
    --[no-]verify-signatures
                          verify that the named commit has a valid GPG signature
    --[no-]autostash      automatically stash/stash pop before and after
    -s, --[no-]strategy <strategy>
                          merge strategy to use
    -X, --[no-]strategy-option <option=value>
                          option for selected merge strategy
    -S, --[no-]gpg-sign[=<key-id>]
                          GPG sign commit
    --[no-]allow-unrelated-histories
                          allow merging unrelated histories

Options related to fetching
    --[no-]all            fetch from all remotes
    -a, --[no-]append     append to .git/FETCH_HEAD instead of overwriting
    --[no-]upload-pack <path>
                          path to upload pack on remote end
    -f, --[no-]force      force overwrite of local branch
    -t, --[no-]tags       fetch all tags and associated objects
    -p, --[no-]prune      prune remote-tracking branches no longer on remote
    -j, --[no-]jobs[=<n>] number of submodules pulled in parallel
    --[no-]dry-run        dry run
    -k, --[no-]keep       keep downloaded pack
    --[no-]depth <depth>  deepen history of shallow clone
    --[no-]shallow-since <time>
                          deepen history of shallow repository based on time
    --[no-]shallow-exclude <ref>
                          deepen history of shallow clone, excluding ref
    --[no-]deepen <n>     deepen history of shallow clone
    --unshallow           convert to a complete repository
    --[no-]update-shallow accept refs that update .git/shallow
    --refmap <refmap>     specify fetch refmap
    -o, --[no-]server-option <server-specific>
                          option to transmit
    -4, --[no-]ipv4       use IPv4 addresses only
    -6, --[no-]ipv6       use IPv6 addresses only
    --[no-]negotiation-tip <revision>
                          report that we have only objects reachable from this object
    --[no-]show-forced-updates
                          check for forced-updates on all updated branches
    --[no-]set-upstream   set upstream for git pull/fetch

(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % git push
Enumerating objects: 22, done.
Counting objects: 100% (22/22), done.
Delta compression using up to 8 threads
Compressing objects: 100% (11/11), done.
Writing objects: 100% (12/12), 5.21 KiB | 5.21 MiB/s, done.
Total 12 (delta 6), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (6/6), completed with 6 local objects.
To https://github.com/Vishnudev1702/INT332.git
   120ac1f..4648408  main -> main
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % cd ~/docker-maven-demo
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % mvn clean package
WARNING: A terminally deprecated method in sun.misc.Unsafe has been called
WARNING: sun.misc.Unsafe::staticFieldBase has been called by com.google.inject.internal.aop.HiddenClassDefiner (file:/opt/homebrew/Cellar/maven/3.9.11/libexec/lib/guice-5.1.0-classes.jar)
WARNING: Please consider reporting this to the maintainers of class com.google.inject.internal.aop.HiddenClassDefiner
WARNING: sun.misc.Unsafe::staticFieldBase will be removed in a future release
[INFO] Scanning for projects...
[INFO] 
[INFO] -------------------< com.example:docker-maven-demo >--------------------
[INFO] Building docker-maven-demo 1.0-SNAPSHOT
[INFO]   from pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- clean:3.2.0:clean (default-clean) @ docker-maven-demo ---
[INFO] Deleting /Users/vishnudevsakthivel/docker-maven-demo/target
[INFO] 
[INFO] --- resources:3.3.1:resources (default-resources) @ docker-maven-demo ---
[WARNING] Using platform encoding (UTF-8 actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] skip non existing resourceDirectory /Users/vishnudevsakthivel/docker-maven-demo/src/main/resources
[INFO] 
[INFO] --- compiler:3.13.0:compile (default-compile) @ docker-maven-demo ---
[INFO] Recompiling the module because of changed source code.
[WARNING] File encoding has not been set, using platform encoding UTF-8, i.e. build is platform dependent!
[INFO] Compiling 1 source file with javac [debug target 17] to target/classes
[WARNING] location of system modules is not set in conjunction with -source 17
  not setting the location of system modules may lead to class files that cannot run on JDK 17
    --release 17 is recommended instead of -source 17 -target 17 because it sets the location of system modules automatically
[INFO] 
[INFO] --- resources:3.3.1:testResources (default-testResources) @ docker-maven-demo ---
[WARNING] Using platform encoding (UTF-8 actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] skip non existing resourceDirectory /Users/vishnudevsakthivel/docker-maven-demo/src/test/resources
[INFO] 
[INFO] --- compiler:3.13.0:testCompile (default-testCompile) @ docker-maven-demo ---
[INFO] Recompiling the module because of changed dependency.
[WARNING] File encoding has not been set, using platform encoding UTF-8, i.e. build is platform dependent!
[INFO] Compiling 1 source file with javac [debug target 17] to target/test-classes
[WARNING] location of system modules is not set in conjunction with -source 17
  not setting the location of system modules may lead to class files that cannot run on JDK 17
    --release 17 is recommended instead of -source 17 -target 17 because it sets the location of system modules automatically
[INFO] 
[INFO] --- surefire:3.2.5:test (default-test) @ docker-maven-demo ---
[INFO] Using auto detected provider org.apache.maven.surefire.junit4.JUnit4Provider
[INFO] 
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running com.example.AppTest
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.014 s -- in com.example.AppTest
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] 
[INFO] --- jar:3.3.0:jar (default-jar) @ docker-maven-demo ---
[INFO] Building jar: /Users/vishnudevsakthivel/docker-maven-demo/target/docker-maven-demo-1.0-SNAPSHOT.jar
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  0.959 s
[INFO] Finished at: 2026-04-24T12:28:35+05:30
[INFO] ------------------------------------------------------------------------
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % open -e Dockerfile
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % docker build -t java-app .
[+] Building 1.9s (9/9) FINISHED                                                                            docker:desktop-linux
 => [internal] load build definition from Dockerfile                                                                        0.0s
 => => transferring dockerfile: 140B                                                                                        0.0s
 => [internal] load metadata for docker.io/library/eclipse-temurin:21-jdk                                                   1.8s
 => [auth] library/eclipse-temurin:pull token for registry-1.docker.io                                                      0.0s
 => [internal] load .dockerignore                                                                                           0.0s
 => => transferring context: 2B                                                                                             0.0s
 => [1/3] FROM docker.io/library/eclipse-temurin:21-jdk@sha256:e58e492628c1428ceb838afc1a1b8762673d5eaa09296f560c363daea0f  0.0s
 => => resolve docker.io/library/eclipse-temurin:21-jdk@sha256:e58e492628c1428ceb838afc1a1b8762673d5eaa09296f560c363daea0f  0.0s
 => [internal] load build context                                                                                           0.0s
 => => transferring context: 2.50kB                                                                                         0.0s
 => CACHED [2/3] WORKDIR /app                                                                                               0.0s
 => [3/3] COPY target/*.jar app.jar                                                                                         0.0s
 => exporting to image                                                                                                      0.1s
 => => exporting layers                                                                                                     0.0s
 => => exporting manifest sha256:20590d5a8503ad5dd5a199284fd1cdc277f71f1d0e34b80fa9a9433982c281e9                           0.0s
 => => exporting config sha256:0d7200ca65f268af1959c9e70de268182d5860dbd7e95a691eb58544cc900f94                             0.0s
 => => exporting attestation manifest sha256:fb4a4617ef58571f87eb4d3451a82bbb438f0ff4f7f12be8981fb3885d29c021               0.0s
 => => exporting manifest list sha256:75444c8c01b6ae583128348c519824859ffab852496c3e5a506f945edf9052cd                      0.0s
 => => naming to docker.io/library/java-app:latest                                                                          0.0s
 => => unpacking to docker.io/library/java-app:latest                                                                       0.0s

View build details: docker-desktop://dashboard/build/desktop-linux/desktop-linux/7q3hqzqzkuh63zcfblml3bsb7
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % docker run -d --name java-container java-app

What's next:
    Debug this container error with Gordon → docker ai "help me fix this container error"
docker: Error response from daemon: Conflict. The container name "/java-container" is already in use by container "2076dd65643a1febdf2890764266d98f5efde00a794902e304e209a08eb5d002". You have to remove (or rename) that container to be able to reuse that name.

Run 'docker run --help' for more information
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % docker rm -f java-container
java-container
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % docker run -d --name java-container java-app
f260dfb22c7cb3476d8eae8cba765d62e7fb1ba684d10ff8a4ad85844af9e5ac
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % docker ps -a
CONTAINER ID   IMAGE                             COMMAND                  CREATED          STATUS                      PORTS                 NAMES
f260dfb22c7c   java-app                          "java -jar app.jar"      12 seconds ago   Exited (0) 11 seconds ago                         java-container
48ceb16bef55   my-docker-app                     "python3 app.py"         24 hours ago     Exited (137) 21 hours ago                         great_tu
9052f447ab1f   e65bc05bb45f                      "python3 app.py"         24 hours ago     Exited (0) 24 hours ago                           stoic_heyrovsky
fabd32df63ab   8dd96dd8874a                      "python3 app.py"         2 days ago       Exited (0) 2 days ago                             loving_pare
95286181dc22   8dd96dd8874a                      "python3 app.py"         2 days ago       Exited (0) 2 days ago                             youthful_robinson
57350d6bbb7b   docker-maven-demo:1.0-SNAPSHOT    "java -cp @/app/jib-…"   9 days ago       Exited (0) 9 days ago                             vigorous_einstein
6d48ca68d84f   docker-maven-demo:latest          "java -cp @/app/jib-…"   9 days ago       Exited (0) 9 days ago                             exciting_leakey
917b9113346d   docker-maven-demo:latest          "java -cp @/app/jib-…"   9 days ago       Exited (0) 9 days ago                             sharp_vaughan
35eddf3ae1bb   maven:3.9.10-eclipse-temurin-17   "/usr/local/bin/mvn-…"   2 weeks ago      Exited (0) 2 weeks ago                            myapp-app-1
cb9ed0cdd52f   maven:3.9.10-eclipse-temurin-17   "/usr/local/bin/mvn-…"   2 weeks ago      Exited (0) 2 weeks ago                            maven-build
4113c664dda0   wordpress:latest                  "docker-entrypoint.s…"   2 weeks ago      Exited (137) 2 weeks ago                          wordpress-app
2807d2ecff6f   mysql:8.0                         "docker-entrypoint.s…"   2 weeks ago      Up 18 minutes               3306/tcp, 33060/tcp   mysql-db
d8a247888309   node:18                           "docker-entrypoint.s…"   2 weeks ago      Exited (254) 2 weeks ago                          node-app
2c8a3b178618   mongo:6                           "docker-entrypoint.s…"   2 weeks ago      Exited (0) 2 weeks ago                            mongo-db
4014db77fba3   nginx                             "/docker-entrypoint.…"   6 weeks ago      Exited (0) 6 weeks ago                            docker-web
9e380b7ceda3   ubuntu:latest                     "/bin/bash"              8 weeks ago      Exited (0) 8 weeks ago                            awesome_lumiere
829262f82330   ubuntu                            "/bin/bash"              8 weeks ago      Exited (0) 8 weeks ago                            loving_grothendieck
1ddffb1834fb   ubuntu:latest                     "/bin/bash"              8 weeks ago      Exited (0) 8 weeks ago                            intelligent_margulis
883c660b41e4   mysql                             "docker-entrypoint.s…"   2 months ago     Exited (137) 2 months ago                         mysql-test
d215223b073f   mysql:8                           "docker-entrypoint.s…"   2 months ago     Exited (1) 2 months ago                           intelligent_banach
906f6fcabd13   mysql:8                           "docker-entrypoint.s…"   2 months ago     Exited (1) 2 months ago                           intelligent_blackwell
1635b4a2f14c   httpd                             "env"                    2 months ago     Exited (0) 2 months ago                           romantic_archimedes
0bd1caefda61   ubuntu                            "/bin/bash"              2 months ago     Exited (137) 2 months ago                         mycontainer
acb9028d3633   httpd                             "httpd-foreground"       2 months ago     Exited (137) 2 months ago                         college_portal
79ecc8dec461   httpd                             "httpd-foreground"       2 months ago     Created                                           angry_clarke
4cca560e4eb5   httpd                             "httpd-foreground"       2 months ago     Exited (0) 2 months ago                           recursing_wing
7d62db6fb174   mongo                             "docker-entrypoint.s…"   2 months ago     Exited (0) 2 months ago                           db-app
3db538d4d4f5   httpd                             "httpd-foreground"       2 months ago     Created                                           myapache
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % Thread.sleep(100000);
zsh: unknown file attribute: 1
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % while(true) {}
zsh: missing delimiter for 'u' glob qualifier
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % mvn clean package
docker build -t java-app .
docker run -d --name java-container java-app
WARNING: A terminally deprecated method in sun.misc.Unsafe has been called
WARNING: sun.misc.Unsafe::staticFieldBase has been called by com.google.inject.internal.aop.HiddenClassDefiner (file:/opt/homebrew/Cellar/maven/3.9.11/libexec/lib/guice-5.1.0-classes.jar)
WARNING: Please consider reporting this to the maintainers of class com.google.inject.internal.aop.HiddenClassDefiner
WARNING: sun.misc.Unsafe::staticFieldBase will be removed in a future release
[INFO] Scanning for projects...
[INFO] 
[INFO] -------------------< com.example:docker-maven-demo >--------------------
[INFO] Building docker-maven-demo 1.0-SNAPSHOT
[INFO]   from pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- clean:3.2.0:clean (default-clean) @ docker-maven-demo ---
[INFO] Deleting /Users/vishnudevsakthivel/docker-maven-demo/target
[INFO] 
[INFO] --- resources:3.3.1:resources (default-resources) @ docker-maven-demo ---
[WARNING] Using platform encoding (UTF-8 actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] skip non existing resourceDirectory /Users/vishnudevsakthivel/docker-maven-demo/src/main/resources
[INFO] 
[INFO] --- compiler:3.13.0:compile (default-compile) @ docker-maven-demo ---
[INFO] Recompiling the module because of changed source code.
[WARNING] File encoding has not been set, using platform encoding UTF-8, i.e. build is platform dependent!
[INFO] Compiling 1 source file with javac [debug target 17] to target/classes
[WARNING] location of system modules is not set in conjunction with -source 17
  not setting the location of system modules may lead to class files that cannot run on JDK 17
    --release 17 is recommended instead of -source 17 -target 17 because it sets the location of system modules automatically
[INFO] 
[INFO] --- resources:3.3.1:testResources (default-testResources) @ docker-maven-demo ---
[WARNING] Using platform encoding (UTF-8 actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] skip non existing resourceDirectory /Users/vishnudevsakthivel/docker-maven-demo/src/test/resources
[INFO] 
[INFO] --- compiler:3.13.0:testCompile (default-testCompile) @ docker-maven-demo ---
[INFO] Recompiling the module because of changed dependency.
[WARNING] File encoding has not been set, using platform encoding UTF-8, i.e. build is platform dependent!
[INFO] Compiling 1 source file with javac [debug target 17] to target/test-classes
[WARNING] location of system modules is not set in conjunction with -source 17
  not setting the location of system modules may lead to class files that cannot run on JDK 17
    --release 17 is recommended instead of -source 17 -target 17 because it sets the location of system modules automatically
[INFO] 
[INFO] --- surefire:3.2.5:test (default-test) @ docker-maven-demo ---
[INFO] Using auto detected provider org.apache.maven.surefire.junit4.JUnit4Provider
[INFO] 
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running com.example.AppTest
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.016 s -- in com.example.AppTest
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] 
[INFO] --- jar:3.3.0:jar (default-jar) @ docker-maven-demo ---
[INFO] Building jar: /Users/vishnudevsakthivel/docker-maven-demo/target/docker-maven-demo-1.0-SNAPSHOT.jar
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  0.955 s
[INFO] Finished at: 2026-04-24T12:31:45+05:30
[INFO] ------------------------------------------------------------------------
[+] Building 1.4s (8/8) FINISHED                                                                            docker:desktop-linux
 => [internal] load build definition from Dockerfile                                                                        0.0s
 => => transferring dockerfile: 140B                                                                                        0.0s
 => [internal] load metadata for docker.io/library/eclipse-temurin:21-jdk                                                   1.3s
 => [internal] load .dockerignore                                                                                           0.0s
 => => transferring context: 2B                                                                                             0.0s
 => [1/3] FROM docker.io/library/eclipse-temurin:21-jdk@sha256:e58e492628c1428ceb838afc1a1b8762673d5eaa09296f560c363daea0f  0.0s
 => => resolve docker.io/library/eclipse-temurin:21-jdk@sha256:e58e492628c1428ceb838afc1a1b8762673d5eaa09296f560c363daea0f  0.0s
 => [internal] load build context                                                                                           0.0s
 => => transferring context: 2.50kB                                                                                         0.0s
 => CACHED [2/3] WORKDIR /app                                                                                               0.0s
 => [3/3] COPY target/*.jar app.jar                                                                                         0.0s
 => exporting to image                                                                                                      0.1s
 => => exporting layers                                                                                                     0.0s
 => => exporting manifest sha256:5b01b440357750922dc4205491c7f85762cd7eda98a569f2df534be031772c03                           0.0s
 => => exporting config sha256:708ce6f19c7df94238695374038abdf9832c38e41aad0d4a85e85031e6d65e8f                             0.0s
 => => exporting attestation manifest sha256:982036947738321accef0f60be0b51c32ee8be3b3b6160279838def7d8fdf3a5               0.0s
 => => exporting manifest list sha256:30d1408b796f82e8f9f6ace1f227bf8c6801af02da318927de821150b7a7009c                      0.0s
 => => naming to docker.io/library/java-app:latest                                                                          0.0s
 => => unpacking to docker.io/library/java-app:latest                                                                       0.0s

View build details: docker-desktop://dashboard/build/desktop-linux/desktop-linux/cokdlegtyhtp2o3ws8nbnu397

What's next:
    Debug this container error with Gordon → docker ai "help me fix this container error"
docker: Error response from daemon: Conflict. The container name "/java-container" is already in use by container "f260dfb22c7cb3476d8eae8cba765d62e7fb1ba684d10ff8a4ad85844af9e5ac". You have to remove (or rename) that container to be able to reuse that name.

Run 'docker run --help' for more information
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % docker ps
CONTAINER ID   IMAGE       COMMAND                  CREATED       STATUS          PORTS                 NAMES
2807d2ecff6f   mysql:8.0   "docker-entrypoint.s…"   2 weeks ago   Up 19 minutes   3306/tcp, 33060/tcp   mysql-db
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % docker ps -a
CONTAINER ID   IMAGE                             COMMAND                  CREATED         STATUS                      PORTS                 NAMES
f260dfb22c7c   75444c8c01b6                      "java -jar app.jar"      2 minutes ago   Exited (0) 2 minutes ago                          java-container
48ceb16bef55   my-docker-app                     "python3 app.py"         24 hours ago    Exited (137) 21 hours ago                         great_tu
9052f447ab1f   e65bc05bb45f                      "python3 app.py"         24 hours ago    Exited (0) 24 hours ago                           stoic_heyrovsky
fabd32df63ab   8dd96dd8874a                      "python3 app.py"         2 days ago      Exited (0) 2 days ago                             loving_pare
95286181dc22   8dd96dd8874a                      "python3 app.py"         2 days ago      Exited (0) 2 days ago                             youthful_robinson
57350d6bbb7b   docker-maven-demo:1.0-SNAPSHOT    "java -cp @/app/jib-…"   9 days ago      Exited (0) 9 days ago                             vigorous_einstein
6d48ca68d84f   docker-maven-demo:latest          "java -cp @/app/jib-…"   9 days ago      Exited (0) 9 days ago                             exciting_leakey
917b9113346d   docker-maven-demo:latest          "java -cp @/app/jib-…"   9 days ago      Exited (0) 9 days ago                             sharp_vaughan
35eddf3ae1bb   maven:3.9.10-eclipse-temurin-17   "/usr/local/bin/mvn-…"   2 weeks ago     Exited (0) 2 weeks ago                            myapp-app-1
cb9ed0cdd52f   maven:3.9.10-eclipse-temurin-17   "/usr/local/bin/mvn-…"   2 weeks ago     Exited (0) 2 weeks ago                            maven-build
4113c664dda0   wordpress:latest                  "docker-entrypoint.s…"   2 weeks ago     Exited (137) 2 weeks ago                          wordpress-app
2807d2ecff6f   mysql:8.0                         "docker-entrypoint.s…"   2 weeks ago     Up 20 minutes               3306/tcp, 33060/tcp   mysql-db
d8a247888309   node:18                           "docker-entrypoint.s…"   2 weeks ago     Exited (254) 2 weeks ago                          node-app
2c8a3b178618   mongo:6                           "docker-entrypoint.s…"   2 weeks ago     Exited (0) 2 weeks ago                            mongo-db
4014db77fba3   nginx                             "/docker-entrypoint.…"   6 weeks ago     Exited (0) 6 weeks ago                            docker-web
9e380b7ceda3   ubuntu:latest                     "/bin/bash"              8 weeks ago     Exited (0) 8 weeks ago                            awesome_lumiere
829262f82330   ubuntu                            "/bin/bash"              8 weeks ago     Exited (0) 8 weeks ago                            loving_grothendieck
1ddffb1834fb   ubuntu:latest                     "/bin/bash"              8 weeks ago     Exited (0) 8 weeks ago                            intelligent_margulis
883c660b41e4   mysql                             "docker-entrypoint.s…"   2 months ago    Exited (137) 2 months ago                         mysql-test
d215223b073f   mysql:8                           "docker-entrypoint.s…"   2 months ago    Exited (1) 2 months ago                           intelligent_banach
906f6fcabd13   mysql:8                           "docker-entrypoint.s…"   2 months ago    Exited (1) 2 months ago                           intelligent_blackwell
1635b4a2f14c   httpd                             "env"                    2 months ago    Exited (0) 2 months ago                           romantic_archimedes
0bd1caefda61   ubuntu                            "/bin/bash"              2 months ago    Exited (137) 2 months ago                         mycontainer
acb9028d3633   httpd                             "httpd-foreground"       2 months ago    Exited (137) 2 months ago                         college_portal
79ecc8dec461   httpd                             "httpd-foreground"       2 months ago    Created                                           angry_clarke
4cca560e4eb5   httpd                             "httpd-foreground"       2 months ago    Exited (0) 2 months ago                           recursing_wing
7d62db6fb174   mongo                             "docker-entrypoint.s…"   2 months ago    Exited (0) 2 months ago                           db-app
3db538d4d4f5   httpd                             "httpd-foreground"       2 months ago    Created                                           myapache
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % docker logs java-container
Hello from Docker + Maven Integration!
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % public static void main(String[] args) throws Exception {
    System.out.println("Hello from Docker + Maven Integration!");
    Thread.sleep(600000); // keeps container alive
}
dquote> 
dquote> 
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % mvn clean package
docker build -t java-app .
WARNING: A terminally deprecated method in sun.misc.Unsafe has been called
WARNING: sun.misc.Unsafe::staticFieldBase has been called by com.google.inject.internal.aop.HiddenClassDefiner (file:/opt/homebrew/Cellar/maven/3.9.11/libexec/lib/guice-5.1.0-classes.jar)
WARNING: Please consider reporting this to the maintainers of class com.google.inject.internal.aop.HiddenClassDefiner
WARNING: sun.misc.Unsafe::staticFieldBase will be removed in a future release
[INFO] Scanning for projects...
[INFO] 
[INFO] -------------------< com.example:docker-maven-demo >--------------------
[INFO] Building docker-maven-demo 1.0-SNAPSHOT
[INFO]   from pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- clean:3.2.0:clean (default-clean) @ docker-maven-demo ---
[INFO] Deleting /Users/vishnudevsakthivel/docker-maven-demo/target
[INFO] 
[INFO] --- resources:3.3.1:resources (default-resources) @ docker-maven-demo ---
[WARNING] Using platform encoding (UTF-8 actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] skip non existing resourceDirectory /Users/vishnudevsakthivel/docker-maven-demo/src/main/resources
[INFO] 
[INFO] --- compiler:3.13.0:compile (default-compile) @ docker-maven-demo ---
[INFO] Recompiling the module because of changed source code.
[WARNING] File encoding has not been set, using platform encoding UTF-8, i.e. build is platform dependent!
[INFO] Compiling 1 source file with javac [debug target 17] to target/classes
[WARNING] location of system modules is not set in conjunction with -source 17
  not setting the location of system modules may lead to class files that cannot run on JDK 17
    --release 17 is recommended instead of -source 17 -target 17 because it sets the location of system modules automatically
[INFO] 
[INFO] --- resources:3.3.1:testResources (default-testResources) @ docker-maven-demo ---
[WARNING] Using platform encoding (UTF-8 actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] skip non existing resourceDirectory /Users/vishnudevsakthivel/docker-maven-demo/src/test/resources
[INFO] 
[INFO] --- compiler:3.13.0:testCompile (default-testCompile) @ docker-maven-demo ---
[INFO] Recompiling the module because of changed dependency.
[WARNING] File encoding has not been set, using platform encoding UTF-8, i.e. build is platform dependent!
[INFO] Compiling 1 source file with javac [debug target 17] to target/test-classes
[WARNING] location of system modules is not set in conjunction with -source 17
  not setting the location of system modules may lead to class files that cannot run on JDK 17
    --release 17 is recommended instead of -source 17 -target 17 because it sets the location of system modules automatically
[INFO] 
[INFO] --- surefire:3.2.5:test (default-test) @ docker-maven-demo ---
[INFO] Using auto detected provider org.apache.maven.surefire.junit4.JUnit4Provider
[INFO] 
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running com.example.AppTest
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.016 s -- in com.example.AppTest
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] 
[INFO] --- jar:3.3.0:jar (default-jar) @ docker-maven-demo ---
[INFO] Building jar: /Users/vishnudevsakthivel/docker-maven-demo/target/docker-maven-demo-1.0-SNAPSHOT.jar
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  0.971 s
[INFO] Finished at: 2026-04-24T12:34:14+05:30
[INFO] ------------------------------------------------------------------------
[+] Building 1.8s (9/9) FINISHED                                                                            docker:desktop-linux
 => [internal] load build definition from Dockerfile                                                                        0.0s
 => => transferring dockerfile: 140B                                                                                        0.0s
 => [internal] load metadata for docker.io/library/eclipse-temurin:21-jdk                                                   1.6s
 => [auth] library/eclipse-temurin:pull token for registry-1.docker.io                                                      0.0s
 => [internal] load .dockerignore                                                                                           0.0s
 => => transferring context: 2B                                                                                             0.0s
 => [1/3] FROM docker.io/library/eclipse-temurin:21-jdk@sha256:e58e492628c1428ceb838afc1a1b8762673d5eaa09296f560c363daea0f  0.0s
 => => resolve docker.io/library/eclipse-temurin:21-jdk@sha256:e58e492628c1428ceb838afc1a1b8762673d5eaa09296f560c363daea0f  0.0s
 => [internal] load build context                                                                                           0.0s
 => => transferring context: 2.50kB                                                                                         0.0s
 => CACHED [2/3] WORKDIR /app                                                                                               0.0s
 => [3/3] COPY target/*.jar app.jar                                                                                         0.0s
 => exporting to image                                                                                                      0.1s
 => => exporting layers                                                                                                     0.0s
 => => exporting manifest sha256:859d44b1179974efc50c747a573b509375ffee4c2b48a13b265980530f867ce0                           0.0s
 => => exporting config sha256:ea91dd1b919871418f72083388e3ec8386bd91c1527e2baee95a102e3200a9c2                             0.0s
 => => exporting attestation manifest sha256:0e44ccebf71863209bc199a3e05ea29d681370da337e2b2c7823f0e07a4ab6d2               0.0s
 => => exporting manifest list sha256:8c290b112d457dc889fdf4d7a069f775180ac66bf1e9f573d2063e1d42e97764                      0.0s
 => => naming to docker.io/library/java-app:latest                                                                          0.0s
 => => unpacking to docker.io/library/java-app:latest                                                                       0.0s

View build details: docker-desktop://dashboard/build/desktop-linux/desktop-linux/u62bzd8raskmtlgaxe2cz2ay1
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % docker rm -f java-container
java-container
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % docker run -d --name java-container java-app
b7d2284685c42f4db39e496427630cf47db721f35470abc8c3a158088f637710
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % docker ps
CONTAINER ID   IMAGE       COMMAND                  CREATED       STATUS          PORTS                 NAMES
2807d2ecff6f   mysql:8.0   "docker-entrypoint.s…"   2 weeks ago   Up 22 minutes   3306/tcp, 33060/tcp   mysql-db
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % open -e src/main/java/com/example/App.java
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % mvn clean package
WARNING: A terminally deprecated method in sun.misc.Unsafe has been called
WARNING: sun.misc.Unsafe::staticFieldBase has been called by com.google.inject.internal.aop.HiddenClassDefiner (file:/opt/homebrew/Cellar/maven/3.9.11/libexec/lib/guice-5.1.0-classes.jar)
WARNING: Please consider reporting this to the maintainers of class com.google.inject.internal.aop.HiddenClassDefiner
WARNING: sun.misc.Unsafe::staticFieldBase will be removed in a future release
[INFO] Scanning for projects...
[INFO] 
[INFO] -------------------< com.example:docker-maven-demo >--------------------
[INFO] Building docker-maven-demo 1.0-SNAPSHOT
[INFO]   from pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- clean:3.2.0:clean (default-clean) @ docker-maven-demo ---
[INFO] Deleting /Users/vishnudevsakthivel/docker-maven-demo/target
[INFO] 
[INFO] --- resources:3.3.1:resources (default-resources) @ docker-maven-demo ---
[WARNING] Using platform encoding (UTF-8 actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] skip non existing resourceDirectory /Users/vishnudevsakthivel/docker-maven-demo/src/main/resources
[INFO] 
[INFO] --- compiler:3.13.0:compile (default-compile) @ docker-maven-demo ---
[INFO] Recompiling the module because of changed source code.
[WARNING] File encoding has not been set, using platform encoding UTF-8, i.e. build is platform dependent!
[INFO] Compiling 1 source file with javac [debug target 17] to target/classes
[WARNING] location of system modules is not set in conjunction with -source 17
  not setting the location of system modules may lead to class files that cannot run on JDK 17
    --release 17 is recommended instead of -source 17 -target 17 because it sets the location of system modules automatically
[INFO] 
[INFO] --- resources:3.3.1:testResources (default-testResources) @ docker-maven-demo ---
[WARNING] Using platform encoding (UTF-8 actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] skip non existing resourceDirectory /Users/vishnudevsakthivel/docker-maven-demo/src/test/resources
[INFO] 
[INFO] --- compiler:3.13.0:testCompile (default-testCompile) @ docker-maven-demo ---
[INFO] Recompiling the module because of changed dependency.
[WARNING] File encoding has not been set, using platform encoding UTF-8, i.e. build is platform dependent!
[INFO] Compiling 1 source file with javac [debug target 17] to target/test-classes
[WARNING] location of system modules is not set in conjunction with -source 17
  not setting the location of system modules may lead to class files that cannot run on JDK 17
    --release 17 is recommended instead of -source 17 -target 17 because it sets the location of system modules automatically
[INFO] 
[INFO] --- surefire:3.2.5:test (default-test) @ docker-maven-demo ---
[INFO] Using auto detected provider org.apache.maven.surefire.junit4.JUnit4Provider
[INFO] 
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running com.example.AppTest
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.021 s -- in com.example.AppTest
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] 
[INFO] --- jar:3.3.0:jar (default-jar) @ docker-maven-demo ---
[INFO] Building jar: /Users/vishnudevsakthivel/docker-maven-demo/target/docker-maven-demo-1.0-SNAPSHOT.jar
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  0.939 s
[INFO] Finished at: 2026-04-24T12:35:53+05:30
[INFO] ------------------------------------------------------------------------
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % docker build -t java-app .
[+] Building 1.5s (8/8) FINISHED                                                                            docker:desktop-linux
 => [internal] load build definition from Dockerfile                                                                        0.0s
 => => transferring dockerfile: 140B                                                                                        0.0s
 => [internal] load metadata for docker.io/library/eclipse-temurin:21-jdk                                                   1.3s
 => [internal] load .dockerignore                                                                                           0.0s
 => => transferring context: 2B                                                                                             0.0s
 => [1/3] FROM docker.io/library/eclipse-temurin:21-jdk@sha256:e58e492628c1428ceb838afc1a1b8762673d5eaa09296f560c363daea0f  0.0s
 => => resolve docker.io/library/eclipse-temurin:21-jdk@sha256:e58e492628c1428ceb838afc1a1b8762673d5eaa09296f560c363daea0f  0.0s
 => [internal] load build context                                                                                           0.0s
 => => transferring context: 2.57kB                                                                                         0.0s
 => CACHED [2/3] WORKDIR /app                                                                                               0.0s
 => [3/3] COPY target/*.jar app.jar                                                                                         0.0s
 => exporting to image                                                                                                      0.1s
 => => exporting layers                                                                                                     0.0s
 => => exporting manifest sha256:ab4cb25bcee5cbd3c89c0e3f65889eddd754df384867604b936c8e805bf28967                           0.0s
 => => exporting config sha256:90987d8b26842a0fca6fea7f1a0b129563d43daf3ff1603963f00aa3823396e5                             0.0s
 => => exporting attestation manifest sha256:464454a481479f4282590747ad6506f64b208dacb4523935356be4c16c80063c               0.0s
 => => exporting manifest list sha256:551fd3b0704315b97c30dcae71036a3362ea40cd8da0bdf42052f3b0c71a854f                      0.0s
 => => naming to docker.io/library/java-app:latest                                                                          0.0s
 => => unpacking to docker.io/library/java-app:latest                                                                       0.0s

View build details: docker-desktop://dashboard/build/desktop-linux/desktop-linux/jyjrzch2hwc9icbv59usevqd2
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % docker rm -f java-container
java-container
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % docker run -d --name java-container java-app
79a6aeda2d2ad01cfe1154162e28df771c80654fdf7653badacc6e8a5e39ff6d
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % docker ps
CONTAINER ID   IMAGE       COMMAND                  CREATED         STATUS          PORTS                 NAMES
79a6aeda2d2a   java-app    "java -jar app.jar"      6 seconds ago   Up 5 seconds                          java-container
2807d2ecff6f   mysql:8.0   "docker-entrypoint.s…"   2 weeks ago     Up 23 minutes   3306/tcp, 33060/tcp   mysql-db
(base) vishnudevsakthivel@Vishnudevs-MacBook-Air docker-maven-demo % docker logs java-container
Hello from Docker + Maven Integration!