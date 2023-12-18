# epr-webapps-code-deploy-pipelines 

This repository hosts the common pipeline templates used in EPR - RPD.

## EPR Single Pipeline

The single deployment pipeline is described by the epr-mass-deployment.yaml file and can be run through ADO under pipelines -> Ops -> epr-single-pipelines

### Dependencies

This pipeline first does a config update through:

* RWD-CPR-EPR4P-ADO/epr-app-config-settings

Then deploys applications using variables depending on:

* RWD-CPR-EPR4P-ADO/frontend-accountcreation-microservice
* RWD-CPR-EPR4P-ADO/frontend-accountmanagement-microservice
* RWD-CPR-EPR4P-ADO/epr_pom_func_submission_check_splitter
* RWD-CPR-EPR4P-ADO/epr_packaging_frontend
* RWD-CPR-EPR4P-ADO/epr-regulator-enrolment-frontend
* RWD-CPR-EPR4P-ADO/epr_regulator_service
* RWD-CPR-EPR4P-ADO/epr_regulator_service_facade
* RWD-CPR-EPR4P-ADO/facade-account-microservice
* RWD-CPR-EPR4P-ADO/epr-obligationchecker-frontend
* RWD-CPR-EPR4P-ADO/epr-anti-virus-function-app
* RWD-CPR-EPR4P-ADO/epr-event-dispatcher-function-app
* RWD-CPR-EPR4P-ADO/epr_pom_api_submission_status
* RWD-CPR-EPR4P-ADO/epr_pom_api_web
* RWD-CPR-EPR4P-ADO/epr_pom_func_producer_validation
* RWD-CPR-EPR4P-ADO/epr-registration-validation-function-app
* RWD-CPR-EPR4P-ADO/backend-account-microservice

The application repository must have deployment variables in the format of (example):

``` yaml
variables:
  azureSubscription: 'AZD-RWD-DEV5'
  docker.imageName: 'facadeaccountcreationrepository'
  acr.azureContainerRegistryName: 'devrwdinfac1401'
  acr.repositoryName: 'facadeaccountcreationrepository'
  serviceName: 'devrwdwebwa5404'
```

## Contributing to this project

Please read the [contribution guidelines](/CONTRIBUTING.md) before submitting a pull request.

## Licence

THIS INFORMATION IS LICENSED UNDER THE CONDITIONS OF THE OPEN GOVERNMENT LICENCE found at:

<http://www.nationalarchives.gov.uk/doc/open-government-licence/version/3>

The following attribution statement MUST be cited in your products and applications when using this information.

>Contains public sector information licensed under the Open Government licence v3

### About the licence

The Open Government Licence (OGL) was developed by the Controller of Her Majesty's Stationery Office (HMSO) to enable information providers in the public sector to license the use and re-use of their information under a common open licence.

It is designed to encourage use and re-use of information freely and flexibly, with only a few conditions.
