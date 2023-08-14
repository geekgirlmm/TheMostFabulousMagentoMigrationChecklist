# TheMostFabulousMagentoMigrationChecklist
Ummm name says it all TheMostFabulousMagentoMigrationChecklist. This is a checklist you can use for migrating Magento to a different host. 
### Match Service Versions
<details>
  <summary>Just do it: PHP, MySQL, Redis, Varnish, ElasticSearch, OpenSearch, RabbitMQ</summary>
  
  1. PHP
     ```
     php -v
     ```
     
  3. MySQL
     ```
     mysql --version
     ```
     
  5. Redis
     ```
     redis-cli --version
     ```
     
  7. Varnish
     ```
     varnishstat -V
     ```
     
  9. ElasticSearch
  10. OpenSearch
      Version check:
      ```
      curl -X GET http://localhost:9200 -u 'admin:admin'
      ```
      Installation:
      ```
      curl -o- https://artifacts.opensearch.org/publickeys/opensearch.pgp | sudo apt-key add -
      echo "deb https://artifacts.opensearch.org/releases/bundle/opensearch/2.x/apt stable main" | sudo tee           /etc/apt/sources.list.d/opensearch-2.x.list
      sudo apt update
      sudo apt list -a opensearch
      sudo apt -y install opensearch=2.5.0
      sudo systemctl enable opensearch
      nano /etc/opensearch/opensearch.yml
	      #change 'plugins.security.ssl.http.enabled' true to false
      sudo systemctl start opensearch
      ```

      Set Magento to use OpenSearch under stores->configuration->catalog->catalog
      (default HTTP Auth is admin/admin)
      
  12. RabbitMQ

</details>


### Symlinks, file ownership and permission
<details>
  <summary>Things that will confuse you later if you don't check now: Symlinks, file ownership, file permission</summary>
  
  1. Symlinks
  2. file ownership
  3. file permission

</details>

### Dumping the database
<details>
  <summary>Meat and potatoes: How, where, tips, troubleshooting</summary>
  
  1. How
  2. Where
  3. Tips
  4. Troubleshooting

</details>

### Copying the files
<details>
  <summary>Go get some coffee, this is Magento: rsync or dumps</summary>
  
  1. Rsync in all its splendor
  2. Dumps if you must

</details>

### Importing the database
<details>
  <summary>Hello Database, come on in: Importing, Definers</summary>
  
  1. Import
  2. Definers

</details>

### BEFORE changing config or reindexing
<details>
  <summary>For the love of all things Magento: modules</summary>
  
  1. Why shouldn't I reindex yet? 
  2. Special Modules

</details>

### Setting Magento services in ENV or via bin/magento
<details>
  <summary>For the love of all things Magento: modules</summary>
  
  1. Why shouldn't I reindex yet? 
  2. Modules

</details>

### FishPig, certain themes, SEO and other oddities
<details>
  <summary>What if your fishes and pigs are running amuck?</summary>
  
  1. FishPig
  2. Pearl theme
  3. SEO

</details>

### Does it all work
<details>
  <summary>You mean you haven't checked?: </summary>
  
1. Logins
2. Checkout
3. Add to Cart

</details>

### Optimization
<details>
  <summary>Why you slow Magento?: caching, indexes, other </summary>
  
  1. Caching
  2. Indexes
  3. Other

</details>
