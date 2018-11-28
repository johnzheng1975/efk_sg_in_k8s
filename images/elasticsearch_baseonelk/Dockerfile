FROM docker.elastic.co/elasticsearch/elasticsearch-oss:6.2.4

COPY config/sg/ config/sg/
COPY bin/ bin/

RUN /usr/share/elasticsearch/bin/elasticsearch-plugin install -b com.floragunn:search-guard-6:6.2.4-23.0
RUN chmod +x plugins/search-guard-6/tools/*.sh \
	&& chown -R elasticsearch config/sg/ \
	&& chmod -R go= config/sg/

COPY config/elasticsearch.yml /usr/share/elasticsearch/config/elasticsearch.yml
RUN chmod 444 /usr/share/elasticsearch/config/elasticsearch.yml
