# Step 3: Search Documents in an Amazon ES Domain<a name="es-gsg-search"></a>

To search documents in an Amazon ES domain, use the Elasticsearch [search](https://www.elastic.co/guide/en/elasticsearch/reference/current/_the_search_api.html) API\. Alternatively, you can use [Kibana](es-kibana.md#es-managedomains-kibana) to search documents in the domain\.

**Note**  
Requests using curl are unauthenticated and rely on an IP\-based access policy\.

**To search documents from the command line**

+ Run the following command to search the *movies* domain for the word *mars*:

  ```
  curl -XGET 'elasticsearch_domain_endpoint/movies/_search?q=mars'
  ```

**To search documents from an Amazon ES domain by using Kibana \(console\)**

1. Point your browser to the Kibana plugin for your Amazon ES domain\. You can find the Kibana endpoint on your domain dashboard on the Amazon ES console\. The URL follows the format of:

   ```
   https://domain.region.es.amazonaws.com/_plugin/kibana/
   ```

1. To use Kibana, you must configure at least one index pattern\. Kibana uses these patterns to identity which indices you want to analyze\. For this tutorial, enter *movies* and choose **Create**\.

1. The **Index Patterns** screen shows your various document fields, fields like `actor` and `director`\. For now, choose **Discover** to search your data\.

1. In the search bar, type *mars*, and then press **Enter**\. Note how the similarity score \(`_score`\) increases when you search for the phrase *mars attacks*\.