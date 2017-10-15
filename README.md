# Angular + Elasticsearch Example vCustom

This is an example project designed to show how you can use elasticsearch.js with angular.

## Prerequisites

In order to run this example, you will need to have the following installed
  1. [elasticsearch](http://www.elasticsearch.org/guide/en/elasticsearch/guide/current/_installing_elasticsearch.html)
  2. [node.js (with npm)](https://docs.npmjs.com/getting-started/installing-node)
  3. [Logstash](https://www.elastic.co/downloads/logstash)
  4. Optional [Kibana](https://www.elastic.co/jp/downloads/kibana)


5. Install the node modules and run other necessary modules 

packages used 
    "angular": "^1.5.5",
    "bootstrap": "^3.3.6",
    "elasticsearch-browser": "^12.0.0-rc2",
    "http-server": "^0.10.0"

  npm install
  from elasticsearch_install_dir/bin ./elasticsearch
  move logstash-sconf.conf to logstash_install_dir/bin and from there
  ./logstash -f logstash-sconf.conf
  optional from kibana_install_dir/bir ./kibana

6. Filling PostgresDB

Open PgAdmin and open frmsbackend and fill in table user with at least this data

INSERT INTO users(first_name, last_name, email, password, phone_number, role)
VALUES ('Joh', 'D', 'john.doe@gmail.com', '$2a$10$b1H5t0FflsFMox0oqgcaQO/J5n9foo05lbA36h17fqj1dEx.yeyW2', '0911111111', 'USER');
INSERT INTO users(first_name, last_name, email, password, phone_number, role)
VALUES ('Jo', 'Do', 'john.doe@gmail.com', '$2a$10$b1H5t0FflsFMox0oqgcaQO/J5n9foo05lbA36h17fqj1dEx.yeyW2', '0911111111', 'USER');
INSERT INTO users(first_name, last_name, email, password, phone_number, role)
VALUES ('John', 'Doe', 'john.doe@gmail.com', '$2a$10$b1H5t0FflsFMox0oqgcaQO/J5n9foo05lbA36h17fqj1dEx.yeyW2', '0911111111', 'USER');

## Running

7. Run this example from this dir

  http-server -a localhost -p 8000

Now you can access Kibana on localhost:5601
 		   elasticsearch node on localhost:9200
                   This app on localhost:8000 


## Conclusion

logstash is pulling data from PostgresDB to elasticsearch intern DB every minute so it is updated every minute (can be changed). 
JSON used as data for filter is much better and faster comparing to normal filter functions for DB however we would need more setting up for first time and one more script needs to run every N amount of time. On frontend it is very easy to set up everything for elasticsearch which I doubt it would be that easy for ordinary filters. Use case would be to remove drop menu which we have now and to put searchbox instead of it and search results would pop in another small window and when pressed on that user/event/company that user/event/company  would be selected just like it is now. Todays problem is when we have over 200 companies it is painful to scroll to them and with this solution we can either scroll them(no filters) or use filter.





  


