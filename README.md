## JTE Plugin for Severell

### Installation

Add the following dependency to your `pom.xml`

```
<dependency>
    <groupId>com.severell.plugins</groupId>
    <artifactId>jte</artifactId>
    <version>0.0.2/version>
</dependency>
```

Then in your `providers.java` you'll need to add the `JteProvider.java`. The provider list should look something like this

```java
    public static ServiceProvider[] load(Container c) {
        return new ServiceProvider[]{
                new AppProvider(c),
                new JettyProvider(c),
                new SessionProvider(c),
                new ViewProvider(c),
                new JteProvider(c),
                new MailProvider(c),
                new RouteProvider(c),
        };
    }
```
Finally in your `.env` file you'll need to add the following variable.

```text
VIEW_DRIVER=Jte
```

### Usage

Now in your controller files you can render your Jte templates.

```java
resp.render("index.jte", new HashMap<String, Object>());
```