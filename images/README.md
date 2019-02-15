# Mo Notes
https://github.com/haraldk/TwelveMonkeys
https://haraldk.github.io/TwelveMonkeys/#manual-dependency-example
bucket: staging.testlab11-221911.appspot.com
http://www.zoftino.com/google-app-engine-java-application-example-using-maven

https://cloud.google.com/java/
https://github.com/googleapis/google-cloud-java/blob/master/google-cloud-examples/src/main/java/com/google/cloud/examples/storage/snippets/StorageSnippets.java
https://googleapis.github.io/google-cloud-java/google-cloud-clients/apidocs/index.html


make public
https://cloud.google.com/storage/docs/access-public-datadragonmosho@cloudshell:~/java-examples/java-docs-samples/appengine-java8/images (testlab11-221911)$ gsutil iam ch allUsers:objectViewer gs://staging.testlab11-221911.appspot.com
dragonmosho@cloudshell:~/java-examples/java-docs-samples/appengine-java8/images (testlab11-221911)$ gsutil iam ch allUsers:objectViewer gs://testlab11-221911.appspot.com
dragonmosho@cloudshell:~ (testlab11-221911)$ gsutil iam ch allUsers:objectViewer gs://staging.testlab11-221911.appspot.com

http://storage.googleapis.com/[BUCKET_NAME]/[OBJECT_NAME]
dragonmosho@cloudshell:~/java-examples/java-docs-samples/appengine-java8/images (testlab11-221911)$ gsutil acl ch -u AllUsers:R gs://staging.testlab11-221911.appspot.com/image.jpg

https://cloud.google.com/appengine/docs/standard/java/googlecloudstorageclient/read-write-to-cloud-storage
https://www.programcreek.com/java-api-examples/index.php?api=com.google.cloud.storage.Bucket

https://stackoverflow.com/questions/1209583/using-java-advanced-imaging-with-maven


   </plugin>
     <groupId>com.google.cloud.tools</groupId>
     <artifactId>appengine-maven-plugin</artifactId>
     <version>1.3.2</version>
   </plugin>
   <plugin>
     <groupId>org.eclipse.jetty</groupId>
     <artifactId>jetty-maven-plugin</artifactId>
     <version>9.3.7.v20160115</version>
   </plugin>

# Google App Engine Standard Environment Images Sample

<a href="https://console.cloud.google.com/cloudshell/open?git_repo=https://github.com/GoogleCloudPlatform/java-docs-samples&page=editor&open_in_editor=appengine-java8/images/README.md">
<img alt="Open in Cloud Shell" src ="http://gstatic.com/cloudssh/images/open-btn.png"></a>

This sample demonstrates how to use the Images Java API.

See the [Google App Engine standard environment documentation][ae-docs] for more
detailed instructions.

[ae-docs]: https://cloud.google.com/appengine/docs/java/

## Modify the app

Using the [Google Cloud SDK](https://cloud.google.com/sdk/) create a bucket

    $ gsutil mb YOUR-PROJECT-ID.appspot.com

* Edit `src/main/java/com/example/appengine/images/ImageServlet.java` and set your `bucket` name.

## Running locally

 This example uses the
 [App Engine maven plugin](https://cloud.google.com/appengine/docs/java/tools/maven).
 To run this sample locally:

     $ mvn appengine:devserver

 To see the results of the sample application, open
 [localhost:8080](http://localhost:8080) in a web browser.


## Deploying

 In the following command, replace YOUR-PROJECT-ID with your
 [Google Cloud Project ID](https://developers.google.com/console/help/new/#projectnumber)
 and SOME-VERSION with a valid version number.

     $ mvn appengine:update -Dappengine.appId=YOUR-PROJECT-ID -Dappengine.version=SOME-VERSION
