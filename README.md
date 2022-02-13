http://appdev.openshift.io/docs/mission-crud-vertx.html


Deploy:

mvn clean fabric8:deploy -Popenshift

Create DB:

oc apply -f src/test/resources/templates/database.yml

Delete all:

oc delete all -l app=booster-crud-vertx

Delete DB:

oc delete -f src/test/resources/templates/database.yml