# aspnetcore-kafka-kerberos
ASP.NET Core image with librdkafka compiled with Kerberos support

## Versioning
Docker images are tagged using following format `.NET Core version`-`librdkafka version`. E.g. 2.1.4-0.11.5 means .NET Core 2.14 with librdkafka 0.11.5

## Using the image (Dockerfile changes)
1. Replace `FROM  microsoft/dotnet:2.1-aspnetcore-runtime` with `FROM shatl/aspnetcore-kafka-kerberos`
2. After copying binaries (assuming `/app` is a target folder) add this line `RUN rm -f /app/runtimes/linux-x64/native/librdkafka.so && ln -f /usr/local/lib/librdkafka.so /app/runtimes/linux-x64/native/librdkafka.so`
