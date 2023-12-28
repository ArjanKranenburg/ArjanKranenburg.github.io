## New techniques: Quarkus

In the past year or so, I’ve been working on Featrz ([featrz.com](https://featrz.com/)). Go ahead take a sneak-preview. You can see some Demo-features by selecting a Project from the top-right corner.

Interesting about this application are the used techniques. Whenever I hear about a new technique on a conference or in a blog, I make a note of it with the intention of trying it out. To see if it is really useful and will work in a real project. Not a Helloworld!-application, but with security, a real database, a CI pipeline, and of course, automated checks. One of those techniques that I noted is [Quarkus](https://quarkus.io/).

Quarkus is “supersonic subatomic java“. And “a Kubernetes Native Java stack tailored for OpenJDK HotSpot and GraalVM, crafted from the best of breed Java libraries and standards“. In my words: it allows for java applications to run inside a container and be fast. And also very handy: you can develop while it is running, seeing immediate effect of your changes.

### Featrz
The Featrz application is about showing Feature Files (Gherkin) in a browser. It starts with cloning a repository and converting the files with the .feature extension to JSON. These JSON blobs are then stored in a NoSQL database and used to display in the GUI.

There are 4 micro-services: a frontend, a server, a converter, and a data-store service. All are build with Quarkus and, except for the data-store, all are running in native-mode, i.e. they are not compiled to java byte-code to run on a JVM, but to an executable for a specific Operating System. That’s not a step back because we run it in a container of which we know the OS and the container itself will give us the portability as well. The containers are deployed in Google Cloud and when needed they will run using Cloud Run.

To illustrate how fast Quarkus is, the conversion happens in real-time. I wanted to store the results to make it even faster, but it turns out that retrieving the data from the database is hardly any faster than converting them again. At least not for the small projects that I used so far.

### Support for libraries
The drawback of Quarkus may be that not all libraries are supported when compiling in Native mode. The Quarkus project is working hard on getting more support for libraries. E.g. instead of using Gson, I had to make my own package to convert my POJO’s to JSON. But I didn’t find it that troublesome either. It forced me to think very well about the design and as long as the POJO’s are simple, which they are, they are my POJO’s, the conversion is easy as well. If there is no other way, you can always run Quarkus in JVM-mode. As I did with the data-store service.

The use of [containers](https://quarkus.io/vision/container-first) also allows me to run the instances in a Kubernetes cluster as well. That makes the application very flexible in where and how to deploy it. Perhaps later I may release this tool or a variant for private Kubernetes clouds as well. Plus I can test the application locally.

### Conclusion
If you’re like me and want to try-out something new in order to really find out if and how this technique works in a real project, I can definitely recommend to try out Quarkus as well. But also if you’re looking for ways to create micro-services in a public or private cloud, Quarkus may be an interesting way to go.