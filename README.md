# Sample project that uses GitLab Maven repository feature


1. Automatically build new snapshot on new push to the master branch
2. Uses Git repo for maven scm plugin (works with mvn release plugin)
3. Supports user access token for command line `mvn deploy`

## Using Maven CLI

To be able to donwload and upload packages from this repo using your local machine 
you need to add `gitlab-com` server section to your `~/.m2/settings.xml`

```xml
<settings xmlns="http://maven.apache.org/SETTINGS/1.1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.1.0 http://maven.apache.org/xsd/settings-1.1.0.xsd">
  <servers>
     <server>
       <id>gitlab-com</id>
       <configuration>
         <httpHeaders>
           <property>
             <name>Private-Token</name>
             <value>XXXXXXXXXX</value>
           </property>
         </httpHeaders>
       </configuration>
     </server>
   </servers>
 </settings>
```

## Forking

Once you fork this project, make sure to replace project URL and ID in `pom.xml`. 
See https://gitlab.com/gitlab-org/examples/mvn-example/commit/e6be5e54893dc882571536979ae209649b21003a for example. 