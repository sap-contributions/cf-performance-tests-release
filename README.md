# CF Performance Tests BOSH Errand

This BOSH errand can be used to run the [CF performance tests](https://github.com/cloudfoundry/cf-performance-tests) in a stable, reproducible environment.

To add the errand to your CF deployment, use this ops file: https://github.com/cloudfoundry/cf-performance-tests-pipeline/operations/performance-tests-errand.yml

After redeployment, you can call the errand with `bosh -d cf run-errand cf-performance-tests-errand`.

The errand uses [package vendoring](https://bosh.io/docs/package-vendoring/) to add the CF CLI v8 and the GoLang 1.21 environment. The performance tests are contained as submodule in the `src` folder. The update of the packages and the submodule and the final release build are done in this pipeline:
https://concourse.app-runtime-interfaces.ci.cloudfoundry.org/teams/capi-team/pipelines/release-performance-tests-errand
