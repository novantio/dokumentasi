# definition
for reverse proxy iis

# command

sample config
```
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
    <system.webServer>
        <rewrite>
            <rules>
                <rule name="ReverseProxyInboundRule1" enabled="true" stopProcessing="false">
                    <match url="(.*)" />
                    <action type="Rewrite" url="http://host.com:8161/{R:1}"  />
                </rule>
            </rules>
        </rewrite>
    </system.webServer>
</configuration>
```
for condition referer contain regex
```
<conditions>
    <add input="{HTTP_REFERER}" pattern=".*(novantio.com|localhost).*" negate="false" />
</conditions>
```

full sample with regex
```
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
    <system.webServer>
        <rewrite>
            <rules>
                <rule name="ReverseProxyInboundRule1" enabled="true" stopProcessing="false">
                    <match url="(.*)" />
                    <action type="Rewrite" url="http://host.com:8161/{R:1}"  />
                    <conditions>
                        <add input="{HTTP_REFERER}" pattern=".*(novantio.com|localhost).*" negate="false" />
                    </conditions>
                </rule>
            </rules>
        </rewrite>
    </system.webServer>
</configuration>
```
