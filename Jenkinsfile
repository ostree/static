#!/usr/bin/env groovy

library("govuk")

REPOSITORY = 'static'

node {
  // Deployed by Puppet's Govuk_jenkins::Pipeline manifest

  govuk.buildProject(
    sassLint: false,
    rubyLintDiff: false,
    overrideTestTask: {
      stage("Test") {
        govuk.runTests("test")
        govuk.runTests("jasmine:ci")
      }
    },
    publishingE2ETests: true,
    brakeman: true,
  )
}
