#
# Copyright (c) 2009-2018. Authors: see NOTICE file.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#      http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#

ARG FROM_NAMESPACE
ARG FROM_VERSION
FROM ${FROM_NAMESPACE}/tomcat7:$FROM_VERSION

RUN rm -r /var/lib/tomcat7/webapps/* && \
    cd /var/lib/tomcat7/webapps/ && \
    wget -q https://github.com/cytomine/Cytomine-IRIS/releases/download/v1.0/iris.war -O ROOT.war

RUN touch /tmp/addHosts.sh
COPY deploy.sh /tmp/deploy.sh
RUN chmod +x /tmp/deploy.sh

RUN mkdir -p /usr/share/tomcat7/.grails

ENTRYPOINT ["/tmp/deploy.sh"]
