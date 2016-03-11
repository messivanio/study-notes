## Grails Study Notes

## Requirements

    javac -v

## Install

http://sdkman.io/

    curl -s http://get.sdkman.io | bash

    sdk install grails 3.1.2

Obs: Version 3.1.3 [has a bug](http://stackoverflow.com/a/35929230/771578).


## Create an app

    grails create-app APP_NAME

    grails create-app APP_NAME --profile=angular


[.gitignore for grails](https://www.gitignore.io/api/grails) or:

    grails integrate-with --git

  
https://grails.org

    grails console
    grails shell

??????? Error The Grails shell must be run from Gradle using 'gradle shell -q'

**Change dbCreate in application.yml to ''**

## Database Migrations

??????????????????

    grails dbm-generate-changelog changelog.groovy

localhost:8080/APP_NAME/dbdoc

    grails integrate-with --eclipse
    grails integrate-with --itellij
    

## Domain Classes and GORM

????

- Transaction Write-Behinds (Flush)
- Cascade behavior on associations with "belongsTo"
- Lazy Fetched is default


    MyObject.get(1) //returns null if don't exist
    MyObject.read(1) //Read-only state
    MyObject.load(1) //Just a proxy object

    MyObject.list(offset: 2, max: 50)


## Controllers and Server Pages

Scopes: application, session, request, params, flash

    render(view: "index")
    render MyObject.list() as XML
    render MyObject.list() as JSON

    render(contentType: "application/json") {
      hello = "world"
    }

http://....?format=json

    <body>
      <% out << "Hi There!" %>
    </body>

    <body>
      <% = "Hi There!" %>
    </body>


    <% hello = "Hi There!" %>
    <%= hello %>


GSP Scopes: response, out
GSP < JSP

    <body>
      $(4 * 5)
    </body>

    <g:link action="show" id="1">Pac Man</g:link>
    <g:if /> <g:else>
    <g:each />
    <g:link />
    <g:render template="/view/file" />


### Form Tags

    <g:form name="myForm" url="[controller: 'myController', action: 'add']">...</g:form>

### URL Mappins (Routes)


### Grails Security

#### spring-security-core

- CAS -> Single SignOn
- LDAP
- Kerberos

    plugins {
      compile ':spring-security-core:1.2.7.3'
    }

    grails s2-quickstart PACKAGE_NAME User Role
    grails dbm-generate-gorm-changelog createSecurityTables.groovy

update the changelog.groovy file??????

    grails dbm-update

conf/Boostrap.groovy // Like seeds

s2-quickstart has a bug (generates my-sql like code)
To fix: User.groovy, change "`password`" t "password"

    @Secured(['MY_ROLE'])


#### Grails Shiro

    compile ":shiro:1.1.4"

jasypt plugin -> Encryption
Enable "Unlimited Encryption" (on JDK/JRE)

## Questions

- [Complex layouts](http://compiledammit.com/2012/08/10/creating-templates-layouts-in-grails/)
- [Custom General Field and Table Names](http://grails.github.io/grails-doc/2.4.4/guide/GORM.html#customNamingStrategy)
- [DB Reverse Engineering](https://grails.org/plugin/db-reverse-engineer)
- [Enviroments Differences](http://grails.github.io/grails-doc/3.1.2/guide/conf.html#environments)
- [Error Alerts - E-mail](https://www.javacodegeeks.com/2012/07/logback-application-errors-notification.html)
- [Error pages](http://compiledammit.com/2012/11/29/creating-a-custom-grails-error-page-for-production/) 
- [Groovy](http://www.groovy-lang.org)
- [HTTPS](http://grails.github.io/grails-doc/3.1.2/guide/deployment.html#deploymentTasks) -> Use container set up?
- [Java Melody](http://grails.org/plugin/grails-melody)
- [JBoss: Data Sources](http://grails.github.io/grails-doc/3.1.2/guide/conf.html#dataSource)
- [JBoss: Issues](http://grails.org/Deployment) and [generate-jboss-deploy](http://grails-plugins.github.io/grails-jbossas/docs/manual/ref/Scripts/generate-jboss-deploy.html)
- [LDAP](https://grails.org/plugin/spring-security-ldap)
- [Live Reload](https://github.com/livereload/livereload-js#using-livereloadjs)
- [Oracle](http://grails.github.io/grails-doc/3.1.2/guide/conf.html#multipleDatasources)
- [Pagination](https://grails.github.io/grails-doc/latest/ref/Tags/paginate.html)
- [Partials](http://grails.github.io/grails-doc/latest/ref/Tags/render.html)
- [Rest API](http://grails.github.io/grails-doc/3.1.2/guide/webServices.html)
- [Show app version number](http://grails.org/plugin/build-info)
- [War](http://grails.github.io/grails-doc/3.1.2/guide/deployment.html)
- [Works with Windows (OS)?](https://github.com/flofreud/posh-gvm)
- Dates: JodaTime/Lib
- JBoss: System Properties
- No password in dev
- Singleton services -> Use DB or System Properties
- Verify: Eclipse
- Verify: Good user validation error messages 
- Verify: It works behind a proxy?
- Verify: Migration to SQL
- Verify: Page Encoding

## Links

[Introduction to Grails
by Dan Bunker | Pluralsight](https://app.pluralsight.com/library/courses/grails-introduction/table-of-contents)

