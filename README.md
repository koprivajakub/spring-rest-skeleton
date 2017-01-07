# spring rest skeleton

spring-boot based REST skeleton app

#### # installation
 * setup `src/main/resources/application-dev.properties` from template (`src/main/resources/application-dev.template.properties`)
 * run `SPRING_PROFILES_ACTIVE=dev,default mvn spring-boot:run`

#### # supported libs/technologies
 * logging framework (http://logback.qos.ch/)
 * database migrations framework (https://flywaydb.org/)
 * code-generation library (https://projectlombok.org/)
 * [internationalization](#internationalization)
 * [emailing](#emailing)

----

#### `internationalization`
 * app supports i18n messages, just fill them in `src/main/resources/i18n/messages_{locale}.properties`
 * locale is firstly retrieved from *Accept* header and then stored in cookie
 * locale can be changed by *GET* parameter `?setLocale=en`
 * example is available at `GET /test/i18n`  

----

#### `emailing`
 * mailService for sending templatable email messages
 * email supports: thymeleaf templating engine, i18n messages, absolute linked images, attachments
 * you can setup your own mail message template preparator ([example](src/main/java/com/example/service/email/preparator/ExampleMailPreparator.java))
 * usage: `mailService.send(new ExampleMailPreparator());`
