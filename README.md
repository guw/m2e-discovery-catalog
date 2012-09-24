# Testing the M2E discovery catalog

### Update the catalog with your entry

Clone the Git repository containing the catalog entries and publishing mechanism:

```
git clone git@github.com:tesla/m2e-discovery-catalog.git
```

Edit the connectors.xml file with your catalog entry which is [here][1].

### Build the catalog

In the top level of the Git repository execute the following command:

```
mvn clean package
```

This will create the catalog and validate that all the update sites specified are accessible. This will also produce two catalog files that you can use for testing locally with only the file system.

### Test your connector with Eclipse

Specify your newly built catalog by updating the eclipse.ini file in your Eclipse installation

```
-vmargs
...
-Dm2e.discovery.url=file:/path/to/m2e-discovery-catalog/target/classes/catalog-1.1.xml                                                                              
```
Once you have tested your connector and feel that it's working as intended then submit a pull request and we will merge your catalog entry and publish a new catalog.

[1]: https://github.com/tesla/m2e-discovery-catalog/blob/master/org.eclipse.m2e.discovery.oss/connectors.xml