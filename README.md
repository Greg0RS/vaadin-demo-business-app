# Vaadin Demo Business App
![Master Branch](https://github.com/igor-baiborodine/vaadin-demo-business-app/actions/workflows/build.yml/badge.svg?branch=master)

#### This project contains the source code generated by [Vaadin's Starter Pack](https://vaadin.com/start) (Business App Starter)

### Branches
* **master** - Vaadin 14 (updated on April 8th, 2021)
* **V15** - Vaadin 15
* **V13** - Vaadin 13

Business App is a starter for Vaadin. [Live demo](https://business.demo.vaadin.com/)

The starter gives you a productivity boost and a head-start. You get an app shell with a typical hierarchical left-hand menu. The shell, the views and the components are all responsive and touch friendly, which makes them great for desktop and mobile use. The views are built with Java, which enhances Java developers' productivity by allowing them to do all in one language.

The app comes with multiple list views to edit master-detail data. Views can be divided horizontally or vertically to open up the details, and the the details can also be split into multiple tabs for extra space. The details can also be opened fullscreen to maximize the use of space. Additionally there is an opt-in option for opening multiple application views in tabs within the app, for quick comparison or navigation between data. You enable this feature by setting MainLayout.navigationTabs to true.

You can read the detailed documentation in [Vaadin Docs](https://vaadin.com/docs/business-app/overview.html)

## Running the Project in Development Mode

`mvn jetty:run`

Wait for the application to start

Open http://localhost:8080/ to view the application.

## Running the Project in Production Mode

`mvn jetty:run-exploded -Dvaadin.productionMode`

The default mode when the application is built or started is 'development'. The 'production' mode is turned on by setting the `vaadin.productionMode` system property when building or starting the app.

Note that if you switch between running in production mode and development mode, you need to do
```
mvn clean
```
before running in the other mode.

## Running the Project in Production Mode with Docker
```bash
$ docker build --rm -t business-app .
$ docker run --name business-app -d business-app
$ docker logs -f business-app 
```
The application will be available at `http://container-ip:8080/`. To get the container IP address, execute the following command:
```console
$ docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' business-app
```
Via the host machine on port 80:
```console
$ docker run --name business-app -p 80:8080 -d business-app
```
The application will be available at `http://localhost:80/` or `http://host-ip:80/`.

... or with an [image from Docker Hub](https://hub.docker.com/r/ibaiborodine/vaadin-business-app):
```console
$ docker run --name business-app -p 80:8080 -d ibaiborodine/vaadin-business-app
```

## License
A paid Pro or Prime subscription is required for creating a new software project from this starter. After its creation, results can be used, developed and distributed freely, but licenses for the used commercial components are required during development. The starter or its parts cannot be redistributed as a code example or template.

For full terms, see LICENSE
