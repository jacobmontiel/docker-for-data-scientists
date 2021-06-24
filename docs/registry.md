If you have to manage internal images as well, that should not be available from the outside
(e.g., via docker hub), then you should consider running your own in-house registry.
If your setup requires access control or you just want to have a web interface, then I 
can recommend Sonatype's Nexus: 

[https://www.sonatype.com/products/repository-oss](https://www.sonatype.com/products/repository-oss)

**NB:** The open-source version is absolutely sufficient for this purpose 
([OSS vs Pro](https://www.sonatype.com/products/repository-oss-vs-pro-features)).

The biggest advantage of having a local Nexus instance is, that you can use it
as a **proxy** for docker hub. That way, you can pull base images from your local network
rather than having to pull them from a distant server. This makes rebuilding images
very fast, especially if you just removed all images from your machine or moved to a 
new machine.