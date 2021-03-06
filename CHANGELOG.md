# Change Log

All notable changes to this project will be documented in this file.
This project *tries* to adhere to [Semantic Versioning](http://semver.org/), even before v1.0.

## [5.0.7] - 2021-12-18
- [#123](https://github.com/tongueroo/ufo/pull/123) fix activesupport require

## [5.0.6] - 2021-12-16
- [#120](https://github.com/tongueroo/ufo/pull/120) new stack_naming: append_ufo_env default to fix append_env bug
- [#122](https://github.com/tongueroo/ufo/pull/122) require active_support all

## [5.0.5] - 2021-01-23
- allow base profile without a default profile

## [5.0.4] - 2021-01-23
- [#119](https://github.com/tongueroo/ufo/pull/119) layer base profiles with env-specific or default profile

## [5.0.3] - 2020-12-10
- [#118](https://github.com/tongueroo/ufo/pull/118) update aws-mfa-secure with require singleton fix

## [5.0.2]
- #111 Add support of credsStore
- #112 Add support for bridge network mode
- #113 Allow custom container name when you try to attach an existing ELB to a service

## [5.0.1]
- #109 fix fargate
- #110 adjust and document `managed_security_groups` setting

## [5.0.0]
- #104 adjust logs default format to detailed
- #105 major rework: build cfn template with Ruby instead of ERB for new features
- #106 secrets support
- Codified iam_role support with .ufo/iam_roles files: custom and managed policy support. The ECS Task definition was moved into CloudFormation to support this.
- Allow per service security groups
- Conventional .ufo/settings cfn and network files based on ufo env
- Managed_security_groups_enabled=false setting.yml
- Project custom helper methods support
- Add image-override option for ufo ship
- Notification ARN stack cloudformation support for compliance reasons
- update cfn/default to use CamelCase. maintain backward compatibility with underscore. through encourage users to upgrade to CamelCase. There's less mental translation overhead.
- remove pretty option: always pretty

## [4.6.3]
- #101 improve ufo init help

## [4.6.2]
- define texit_on_failure to remove Thor deprecation warning

## [4.6.1]
- #93 Fix firelens functionality
- #97 ufo logs --filter-pattern option
- #98 fix env vars helper to allow surrounding quotes

## [4.6.0]
- #95 Introduce: ufo logs command. Tail logs.
- #96 docs and options

## [4.5.11]
- add mfa support for normal IAM user

## [4.5.10]
- fix .ufo/task_definitions help error message

## [4.5.9]
- fix ufo_env aws_profile tight binding

## [4.5.8]
- #91 added helper scripts to dianose and resolve the SSL issues - added docs to help explain and save the user time and research
- improve cancel command
- update /up check starter example

## [4.5.7]
- #88 update starter variables template with += example

## [4.5.6]
- fix outgoing egress rule to allow ping

## [4.5.5]
- adjust default health check thresholds in skeleton
- improve error handling for UPDATE\_ROLLBACK\_FAILED state

## [4.5.4]
- #85 `ufo docker compile` command. ability to compile Dockerfile from Dockerfile.erb w/o building
- #86 slight improvement to `ufo docker compile`

## [4.5.3]
- fix error exit code when unable to find task definition
- fix upgrade for empty base setting
- improve ufo destroy confirm message
- #82 allow prepend_cluster

## [4.5.2]
- add append_nothing option

## [4.5.1]
- handle UPDATE_IN_PROGRESS stack validation error also
- update comment at top of generated Dockerfile

## [4.5.0]
- #78 append_ufo_env to stack name, new default
- #79 service_cluster map setting
- #80 introduce Docckerfile.erb and dockerfile_variables.yml
- #81 update to zeitwerk for autoloading

## [4.4.3]
- fix edge case when target group name is too long: only occurs with UFO\_FORCE\_TARGET_GROUP mode
- stdout sync true for improved codebuild status
- ufo network init ecs-subnets and elb-subnets options
- update docs: use ecr repo in quick start examples

## [4.4.2]
- fix current_region for codebuild

## [4.4.1]
- return correct exit code 1 when cloudformation deploy fails
- update docs: organize better into subfolders

## [4.4.0]
- #71 from gurpreetatwal/patch-1 remove extra slash from URL
- #73 organize docs better into subfolders
- #74 appending ufo_env to stack name
- change setting aws_profile to tightly bind to ufo_env, simpler to understand

## [4.3.1]
- #70 ps --status filter and fix list_tasks 100 limit issue

## [4.3.0]
- Default starter ecs ec2 template to networkMode awsvpc

## [4.2.1]
- #69 from tls support for network elb

## [4.2.0]
- dont stop tasks on very first deploy, removes edge case error
- update docs: redirection support
- use rainbow gem for terminal colors

## [4.1.10]
- print out failure reason

## [4.1.9]
- print Command failed if task fails

## [4.1.8]
- Merge pull request #59 from everplays/58-ability-to-wait-for-one-off-task-to-finish
- Merge pull request #60 from tongueroo/wait-exit-code

## [4.1.7]
- add scheduling-strategy option #55 from tongueroo/scheduling-strategy

## [4.1.6]
- update bin/deploy starter wrapper
- update quick start with note about ecr image
- update ufo init help

## [4.1.5]
- provide error message and instructions for case of missing default vpc, pull request #49

## [4.1.4]
- improve regexp for striping trailing comments in env files, fixes #47

## [4.1.3]
- build the task definition by default for ufo deploy

## [4.1.2]
- add --build option for ufo deploy

## [4.1.1]
- add --no-register ability to ufo deploy command
- fixes: hide_time_took, ps_spec
- ufo destroy: improve error handling for in progress state
- ufo ps --extra: show shorter container instance arn id

## [4.1.0]
- Merge pull request #46 from tongueroo/ufo-status
- add ufo status command
- ufo ps --extra option
- update docs

## [4.0.3]
- fix ufo ps for stopped task
- improve docs

## [4.0.2]
- Merge pull request #45 from tongueroo/ssl2
- default deregistration_delay 10
- improve ssl support, only create ssl listener when configured

## [4.0.1]
- Merge pull request #44 from tongueroo/ssl
- add listener_ssl resource for better ssl support
- update docs

## [4.0.0]
- Major architecture changes
- Fuller CLI Toolkit Commands
- Load Balancer Support
- Updated Tutorial Guide
- Security Groups
- Improved Fargate Support
- Extra Env Support
- CloudFormation Implementation
- Upgrade Guide
- ECS service created by CloudFormation now
- ELB support: both application and network ELBs
- Route53 support: associates ELB with DNS record
- UFO_ENV_EXTRA concept introduced
- Many additional CLI commands:
- ufo apps
- ufo cancel
- ufo current
- ufo network
- ufo ps
- ufo releases
- ufo resources
- ufo rollback

## [3.5.7]
- display aws ecs run-task command
- fix ufo init in help menu

## [3.5.6]
- upgrade ufo with cli-template, link cli help to website reference help

## [3.5.5]
- Merge pull request #39 from hnatt/fix-docs
- Merge pull request #41 from tongueroo/params-template-scope
- add cloudwatch log info for the task command
- pass template scope to params erb evaluation

## [3.5.4]
- Merge pull request #38 from tongueroo/docker-build-options
- add ability to specify custom docker build options with env UFO_DOCKER_BUILD_OPTIONS variable
- update faq

## [3.5.3]
- Merge pull request #36 from tongueroo/fix-shared-variables-in-task-definitions
- allow usage of shared variables in task_definition blocks again
- dont warn of instance variable collision for template scope variables
- improve builder error message
- improve user error message when task definition block fails to evaluate

## [3.5.2]
- add docs link to params.yml template

## [3.5.1]
- remove helper support for params files. erb still works.

## [3.5.0]
- allow usage of template_definition_method in env variables files

## [3.4.4]
- Merge pull request #34 from tongueroo/show-aws-cli-commands
- Show equivalent cli commands when possible
- Automatically auth ECR when Dockerfiles has ECR image in FROM instruction
- Fix upgrade task and provide user with warning message for 3.4.x version.

## [3.4.3]
- remove debugging puts

## [3.4.2]
- Merge pull request #33 from tongueroo/rubyize_format
- improve rubyize_format so that original log configuration options are kept

## [3.4.1]
- Merge pull request #32 from tongueroo/fix-log-configuration
- fix log configuration dasherization
- Fixes issue #30 how can use syslog as driver for logging?

## [3.4.0]
- Merge pull request #31 fargate support
- ufo upgrade3_3_to_3_4 command
- add params.yml concept to support fargate and any other aws-sdk option
- add TemplateScope class
- combine Default into Util module
- clean up settings method
- display params as helpful info

## [3.3.2]
- Merge pull request #28 from netguru/master
- Fix one off task: ufo task

## [3.3.1]
- fix starter template name

## [3.3.0]
- Merge pull request #27 from tongueroo/template
- add custom templates support
- colorize ufo destroy output

## [3.2.2]
- add .ufo/data to gitignore for upgrade3
- allow system exit to normally happen for rendering error in the task definition
- docs grammar fixes

## [3.2.1]
- ensure settings is always a hash even when settings.yml has nil
- move cli_markdown as development dependency

## [3.2.0]
- pr #23 from tongueroo/cli_markdown: http://ufoships.com/reference/ section now available
- pr #24 from tongueroo/circleci
- pr #25 from tongueroo/ecr-auth-legacy-docker-fix: ecr auth: also write legacy_entry to .docker/config.json
- fix ensure_cluster_exist for inactive cluster bug fix

## [3.1.2]
- upgrade3 updates .gitignore also

## [3.1.1]
- actually use the cluster value in settings
- upgrade variables path also #20

## [3.1.0]
- fix container_info to refer to .ufo instead of old ufo folder  #20
- fix ufo upgrade3 #20
- add render_me_pretty as gemspec dependency, remove vendor/render_me_pretty submodule #20 #18

## [3.0.1]
- add vendor files to gem package: fixes gem install ufo misses 'render_me_pretty' #18

## [3.0.0]
- dotufo: rename ufo folder to .ufo. Use ufo upgrade3 command to upgrade.
- new settings.yml format to account for multiple AWS accounts and environments.
- allows for environment specific setting file
- add auto-completion, to setup: eval $(ufo completion_script)
- ufo upgrade3 command
- ufo init: Use Thor::Group as generator
- default UFO_ENV is now development, not prod
- Merge pull request #9 from jlchenwenbo/master
- Merge branch 'patch-1' of https://github.com/breezeight/ufo into breezeight-patch-1
- Bug: Update ship.rb: list all ecs services instead of just the first page
- replace project_root with Ufo.root internally
- update docs
- use vendorized render_me_pretty for erb rendering

## [2.2.3]
- eval $(ufo completion_script) for tab auto-completion
- default task_definition template fixes: add ecs/ to awslogs_group, add helper.current_region
- move bin/ufo to exe/ufo
- rename: AwsServices to AwsService, Defaults to Default, Settings to Setting

## [2.2.2]
- Remove role passed to create_service. Fixes ufo ship when target-group-arn is provided.

## [2.2.1]
- require aws-sdk-ecr

## [2.2.0]
- only use required aws-sdk components
- allow overriding one off task command
- change default environment to development
- cleanup: help uses markdown files
- starter files: comment out command and fallback to the dockerfile command
- update docs to reflect full env naming
- update generated gitignore
- update help: remove -prod

## [2.1.0]
* ufo init: only require --app and --image option

## [2.0.3]
* add aws log group as a comment in the starter project

## [2.0.2]
* ufo init: update cli help

## [2.0.1]
* ufo init: remove --env option requirement

## [2.0.0]
* shared variable support
* UFO_ENV introduced
* settings: AWS_PROFILE and UFO_ENV mapping to ecs cluster

## [1.7.1]
* only create log group if it doesnt already exist

## [1.7.0]
* automatically create task definintion log group

## [1.6.3]
* fix target_group_prompt

## [1.6.2]
* update bin/deploy starter project script
* update help menu
* update docs

## [1.6.1]
* exit if docker push fails

## [1.6.0]
* rename ufo docker cleanup -> ufo docker clean
* rename ufo docker image_name -> ufo docker name
* add docs

## [1.5.0]
* add ufo ships command
* refactor code into modules: ecr, docker, tasks
* improve error message when task_definitions.rb evaluation errors
* rename --force option to --sure

## [1.2.0]

* allow -h, --help, help options at the end of the command

## [1.1.0]

* print out useful error for ERB template errors

## [1.0.1]

* simplify `ufo task` command option

## [1.0.0]

* add `ufo task` command
* been using in production for a while, ready for 1.0.0 release

## [0.1.6]

* default wait for deployment to false

## [0.1.5]

* helper.env_file instead of env_vars method

## [0.1.2]

* remove byebug dependency and fix task register task

## [0.1.1]

- rename `ufo docker full_image_name` to `ufo docker image_name`

## [0.1.0]

- clean up for initial stable release

## [0.0.5]

- add docker base command
- add docker image cleaners
- service_cluster settings.yml
- Initial conceptual release

