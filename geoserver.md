# definition
for gis data read shapefile (.shp) into rest api

# setup
jetti cross origin
```
<filter>
 <filter-name>cross-origin</filter-name>
 <filter-class>org.eclipse.jetty.servlets.CrossOriginFilter</filter-class>
</filter>
<filter-mapping>
 <filter-name>cross-origin</filter-name>
 <url-pattern>/*</url-pattern>
</filter-mapping>
```

download jetti
```
central.maven.org/maven2/org/eclipse/jetty/jetty-servlets/
```
