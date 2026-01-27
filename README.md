http://appdev.openshift.io/docs/mission-crud-vertx.html

## Local Test

DB_USERNAME=luke DB_PASSWORD=secret mvn vertx:run

## Create DB:

oc apply -f src/test/resources/templates/database.yml

## Deploy App:

mvn clean oc:deploy -Popenshift

## Test

open URL at

oc get route booster-crud-vertx -o jsonpath='{.spec.host}'

## Delete all:

mvn oc:undeploy -Popenshift

(oc delete all -l app=booster-crud-vertx)

## Delete DB:

oc delete -f src/test/resources/templates/database.yml