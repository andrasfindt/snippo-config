# Config Guide

This repository contains config files served by the snippo config server.

## Profiles
Profiles are used to separate configs between environments. Spring Boot applications can apply profiles by setting the `spring.profiles.active` property. When multiple profiles are set, the last profile has the highest precedence.

### Available Profiles
* `RELEASE` - Production release build config
* `SNAPSHOT` - Dev build config
* `PROD` - Production
* `DEV` - DEV  
* `LOCAL` - For local development. Usually used in conjunction with `DEV`

## Refreshing Configs
There are three ways to refresh configs
1. Call the application's `actuator/refresh` endpoint.
2. Restart the application.
3. Call the config server's `refresh-all` endpoint to refresh all applications connected to the hazelcast cluster.

**Note:** Calling the refresh or refresh-all endpoints will only refresh configuration properties in classes annotated with `@RefreshScope` or `@ConfigurationProperties`.


