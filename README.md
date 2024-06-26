# CryptoTest
Complete example of java crypto API

This "test" is able to iterate through all algorithms (even aliases) which every java crypto provider provides.
Every algorithm is initialised, and used. This is probably hugest collection of usages of java crypto api. I'm  afraid some of the apis were not used in last 10 years anywhere else (eg xml parts, as they have much more suitable wrappers in JDK).

## Usage

## Jtregs
A recomanded way to run this is via jtregs. The `run.sh` takes one argument - jdk to test.  Optional second argument is bugid or directory to run.
`run.sh` will download jtreg for you, unless there already is jtreg or unless you set `JTREG_HOME`. If you need custom runner, `JAVA_HOME` is accepted.

Some of the test are using 3rd party agent machie which reply to **kerberos** login responses, set its hostname via `AGENT_HOSTNAME=agent.example.com`, if you do ot wish to run them set ` SKIP_AGENT_TESTS=1`.

### Make

Set tested JDK using JAVA_HOME env. variable e.g.:
```
export JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk
```
To run the whole thing, simply run make:
```
make
```
to set agent hostname, required by some tests, use AGENT_HOSTNAME parameter. (Agent expects to have same krb setup as expected by [jck](https://web.archive.org/web/20201126185131/https://icedtea.classpath.org/wiki/JCKDistilled#kerberos_prep). Use your domain for service prinicpal, e.g. http/service.example.com).
```
make AGENT_HOSTNAME=agent.example.com
```
to skip tests, which require agent, use SKIP_AGENT_TESTS parameter:
```
make SKIP_AGENT_TESTS=1
```
You can list individual tests using:
```
make list-tests
```
To Run some individual test use e.g.:
```
make CipherTests
```

## Credits
 
 This project would never be created without extensive help of
  *  sparkoo@github
  *  oklinov@github
  *  mzezulka@redhat
  *  pmikova@redhat
  *  zzambers@redhat
  *  jvanek@redhat
