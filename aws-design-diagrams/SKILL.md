---
name: aws-design-diagrams
description: For designing/updating/modifying cloud diagrams using plantuml. It handle .puml files.
---

# AWS Design Diagrams

## Instructions

### Write plantuml files for AWS

In order to incorporate and use the AWS Icons for PlantUML resources, !include statements are added to your diagrams.
A common include file/URL defines the base colors, styles, and characteristics for the diagram.
Then additional configuration files can be added to further customize the diagram, followed by the elements used in the diagram.

To get started, include the AWSCommon.puml file from the dist directory in each .puml file or PlantUML diagram.

This can be referenced by a URL directly to this repository, or by including the file locally. To use this repository, use the following:

    !include https://raw.githubusercontent.com/awslabs/aws-icons-for-plantuml/v23.0/dist/AWSCommon.puml

or this if defining the URL:

    !define AWSPuml https://raw.githubusercontent.com/awslabs/aws-icons-for-plantuml/v23.0/dist

This references the latest GitHub release version of the referenced file from GitHub.
It is recommended not to use the main branch, but instead a specific release version.

For consistency of UML diagrams when referencing the files directly via GitHub and not generated locally, it is recommended to use a specific release version.

!include path/to/AWSCommon.puml

Syntax of !include <awslib/AWSCommon.puml> uses the embedded plantuml-stdlib.

After inclusion of the AWSCommon.puml file, there are two different ways to reference resources:

    Use individual include files - Use one file per service or setting. For example:

    !include AWSPuml/Storage/SimpleStorageService.puml

    Use category include file - Single include that contains all services and resources for that category. For example:

    !include AWSPuml/BusinessApplications/all.puml

All of the services can be found in the dist/ directory, which includes the service or product categories and the corresponding puml files.

For example, including these files from the repository (URL), the includes would look like this:

' Define the main location (URL or local file path)
!define AWSPuml https://raw.githubusercontent.com/awslabs/aws-icons-for-plantuml/v23.0/dist
' Include main AWSCommon and then resource files
!include AWSPuml/AWSCommon.puml
!include AWSPuml/BusinessApplications/all.puml
!include AWSPuml/Storage/SimpleStorageService.puml

This defines the macro AWSPuml to point to the root of the dist/ directory, which reduces the size of the include statements.
Next the AWSCommon.puml file is loaded, and then the actual resource files.
In this example, all of the entities in the BusinessApplications directory are added, and then only the SimpleStorageService entity from the Storage directory.

All examples reference the main branch of this repository.
It is recommended that one of the release tags be used for documents.

### AWS icons files
The tree structure of the dist directory with the icon files to use.

dist
├── Analytics
│   ├── all.puml
│   ├── Analytics.puml
│   ├── AthenaDataSourceConnectors.puml
│   ├── Athena.puml
│   ├── CleanRooms.puml
│   ├── CloudSearch.puml
│   ├── CloudSearchSearchDocuments.puml
│   ├── DataExchangeforAPIs.puml
│   ├── DataExchange.puml
│   ├── DataFirehose.puml
│   ├── DataZoneBusinessDataCatalog.puml
│   ├── DataZoneDataPortal.puml
│   ├── DataZoneDataProjects.puml
│   ├── DataZone.puml
│   ├── EMRCluster.puml
│   ├── EMREMREngine.puml
│   ├── EMRHDFSCluster.puml
│   ├── EMR.puml
│   ├── EntityResolution.puml
│   ├── FinSpace.puml
│   ├── GlueAWSGlueforRay.puml
│   ├── GlueCrawler.puml
│   ├── GlueDataBrew.puml
│   ├── GlueDataCatalog.puml
│   ├── GlueDataQuality.puml
│   ├── Glue.puml
│   ├── KinesisDataStreams.puml
│   ├── Kinesis.puml
│   ├── KinesisVideoStreams.puml
│   ├── LakeFormationDataLake.puml
│   ├── LakeFormation.puml
│   ├── ManagedServiceforApacheFlink.puml
│   ├── ManagedStreamingforApacheKafka.puml
│   ├── MSKAmazonMSKConnect.puml
│   ├── OpenSearchServiceClusterAdministratorNode.puml
│   ├── OpenSearchServiceDataNode.puml
│   ├── OpenSearchServiceIndex.puml
│   ├── OpenSearchServiceObservability.puml
│   ├── OpenSearchServiceOpenSearchDashboards.puml
│   ├── OpenSearchServiceOpenSearchIngestion.puml
│   ├── OpenSearchService.puml
│   ├── OpenSearchServiceTraces.puml
│   ├── OpenSearchServiceUltraWarmNode.puml
│   ├── RedshiftAutocopy.puml
│   ├── RedshiftDataSharingGovernance.puml
│   ├── RedshiftDenseComputeNode.puml
│   ├── RedshiftDenseStorageNode.puml
│   ├── RedshiftML.puml
│   ├── Redshift.puml
│   ├── RedshiftQueryEditorv20.puml
│   ├── RedshiftRA3.puml
│   ├── RedshiftStreamingIngestion.puml
│   └── SageMaker.puml
├── ApplicationIntegration
│   ├── all.puml
│   ├── AppFlow.puml
│   ├── ApplicationIntegration.puml
│   ├── AppSync.puml
│   ├── B2BDataInterchange.puml
│   ├── EventBridgeCustomEventBus.puml
│   ├── EventBridgeDefaultEventBus.puml
│   ├── EventBridgeEvent.puml
│   ├── EventBridgePipes.puml
│   ├── EventBridge.puml
│   ├── EventBridgeRule.puml
│   ├── EventBridgeSaasPartnerEvent.puml
│   ├── EventBridgeScheduler.puml
│   ├── EventBridgeSchema.puml
│   ├── EventBridgeSchemaRegistry.puml
│   ├── ExpressWorkflows.puml
│   ├── ManagedWorkflowsforApacheAirflow.puml
│   ├── MQBroker.puml
│   ├── MQ.puml
│   ├── SimpleNotificationServiceEmailNotification.puml
│   ├── SimpleNotificationServiceHTTPNotification.puml
│   ├── SimpleNotificationService.puml
│   ├── SimpleNotificationServiceTopic.puml
│   ├── SimpleQueueServiceMessage.puml
│   ├── SimpleQueueService.puml
│   ├── SimpleQueueServiceQueue.puml
│   └── StepFunctions.puml
├── ArtificialIntelligence
│   ├── all.puml
│   ├── ApacheMXNetonAWS.puml
│   ├── AppStudio.puml
│   ├── ArtificialIntelligence.puml
│   ├── AugmentedAIA2I.puml
│   ├── BedrockAgentCore.puml
│   ├── Bedrock.puml
│   ├── CodeGuru.puml
│   ├── CodeWhisperer.puml
│   ├── ComprehendMedical.puml
│   ├── Comprehend.puml
│   ├── DeepLearningAMIs.puml
│   ├── DeepLearningContainers.puml
│   ├── DeepRacer.puml
│   ├── DevOpsGuruInsights.puml
│   ├── DevOpsGuru.puml
│   ├── ElasticInference.puml
│   ├── Forecast.puml
│   ├── FraudDetector.puml
│   ├── HealthImaging.puml
│   ├── HealthLake.puml
│   ├── HealthOmics.puml
│   ├── HealthScribe.puml
│   ├── Kendra.puml
│   ├── Lex.puml
│   ├── LookoutforEquipment.puml
│   ├── LookoutforVision.puml
│   ├── Monitron.puml
│   ├── Neuron.puml
│   ├── Nova.puml
│   ├── Panorama.puml
│   ├── Personalize.puml
│   ├── Polly.puml
│   ├── PyTorchonAWS.puml
│   ├── Q.puml
│   ├── RekognitionImage.puml
│   ├── Rekognition.puml
│   ├── RekognitionVideo.puml
│   ├── SageMakerAICanvas.puml
│   ├── SageMakerAIGeospatialML.puml
│   ├── SageMakerAIModel.puml
│   ├── SageMakerAINotebook.puml
│   ├── SageMakerAI.puml
│   ├── SageMakerAIShadowTesting.puml
│   ├── SageMakerAITrain.puml
│   ├── SageMakerGroundTruth.puml
│   ├── SageMakerStudioLab.puml
│   ├── TensorFlowonAWS.puml
│   ├── TextractAnalyzeLending.puml
│   ├── Textract.puml
│   ├── Transcribe.puml
│   └── Translate.puml
├── AWSC4Integration.puml
├── AWSCommon.puml
├── AWSExperimental.puml
├── AWSRaw.puml
├── AWSSimplified.puml
├── Blockchain
│   ├── all.puml
│   ├── Blockchain.puml
│   ├── ManagedBlockchainBlockchain.puml
│   └── ManagedBlockchain.puml
├── BusinessApplications
│   ├── all.puml
│   ├── AppFabric.puml
│   ├── BusinessApplications.puml
│   ├── Chime.puml
│   ├── ChimeSDK.puml
│   ├── Connect.puml
│   ├── EndUserMessaging.puml
│   ├── PinpointAPIs.puml
│   ├── PinpointJourney.puml
│   ├── Pinpoint.puml
│   ├── QuickSuite.puml
│   ├── SimpleEmailServiceEmail.puml
│   ├── SimpleEmailService.puml
│   ├── SupplyChain.puml
│   ├── Wickr.puml
│   ├── WorkDocs.puml
│   ├── WorkDocsSDK.puml
│   └── WorkMail.puml
├── CloudFinancialManagement
│   ├── all.puml
│   ├── BillingConductor.puml
│   ├── Budgets.puml
│   ├── CloudFinancialManagement.puml
│   ├── CostandUsageReport.puml
│   ├── CostExplorer.puml
│   ├── ReservedInstanceReporting.puml
│   └── SavingsPlans.puml
├── Compute
│   ├── all.puml
│   ├── AppRunner.puml
│   ├── Batch.puml
│   ├── Bottlerocket.puml
│   ├── ComputeOptimizer2.puml
│   ├── Compute.puml
│   ├── DCV.puml
│   ├── EC2AMI.puml
│   ├── EC2AutoScaling.puml
│   ├── EC2AutoScalingResource.puml
│   ├── EC2AWSMicroserviceExtractorforNET.puml
│   ├── EC2DBInstance.puml
│   ├── EC2ElasticIPAddress.puml
│   ├── EC2ImageBuilder.puml
│   ├── EC2Instance.puml
│   ├── EC2Instances.puml
│   ├── EC2InstancewithCloudWatch.puml
│   ├── EC2.puml
│   ├── EC2Rescue.puml
│   ├── EC2SpotInstance.puml
│   ├── ElasticBeanstalkApplication.puml
│   ├── ElasticBeanstalkDeployment.puml
│   ├── ElasticBeanstalk.puml
│   ├── ElasticFabricAdapter.puml
│   ├── ElasticVMwareService.puml
│   ├── LambdaLambdaFunction.puml
│   ├── Lambda.puml
│   ├── LightsailforResearch.puml
│   ├── Lightsail.puml
│   ├── LocalZones.puml
│   ├── NitroEnclaves.puml
│   ├── Outpostsfamily.puml
│   ├── Outpostsrack.puml
│   ├── Outpostsservers.puml
│   ├── ParallelCluster.puml
│   ├── ParallelComputingService.puml
│   ├── ServerlessApplicationRepository.puml
│   ├── SimSpaceWeaver.puml
│   └── Wavelength.puml
├── Containers
│   ├── all.puml
│   ├── Containers.puml
│   ├── ECSAnywhere.puml
│   ├── EKSAnywhere.puml
│   ├── EKSDistro.puml
│   ├── ElasticContainerRegistryImage.puml
│   ├── ElasticContainerRegistry.puml
│   ├── ElasticContainerRegistryRegistry.puml
│   ├── ElasticContainerServiceContainer1.puml
│   ├── ElasticContainerServiceContainer2.puml
│   ├── ElasticContainerServiceContainer3.puml
│   ├── ElasticContainerServiceCopilotCLI.puml
│   ├── ElasticContainerServiceECSServiceConnect.puml
│   ├── ElasticContainerService.puml
│   ├── ElasticContainerServiceService.puml
│   ├── ElasticContainerServiceTask.puml
│   ├── ElasticKubernetesServiceEKSonOutposts.puml
│   ├── ElasticKubernetesService.puml
│   ├── Fargate.puml
│   └── RedHatOpenShiftServiceonAWS.puml
├── CustomerEnablement
│   ├── Activate.puml
│   ├── all.puml
│   ├── CustomerEnablement.puml
│   ├── IQ.puml
│   ├── ManagedServices.puml
│   ├── ProfessionalServices.puml
│   ├── rePostPrivate.puml
│   ├── rePost.puml
│   ├── Support.puml
│   └── TrainingCertification.puml
├── CustomerExperience
│   ├── all.puml
│   └── CustomerExperience.puml
├── Database
│   ├── all.puml
│   ├── AuroraAmazonAuroraInstanceAlternate.puml
│   ├── AuroraAmazonRDSInstanceAlternate.puml
│   ├── AuroraAmazonRDSInstance.puml
│   ├── AuroraInstance.puml
│   ├── AuroraMariaDBInstanceAlternate.puml
│   ├── AuroraMariaDBInstance.puml
│   ├── AuroraMySQLInstanceAlternate.puml
│   ├── AuroraMySQLInstance.puml
│   ├── AuroraOracleInstanceAlternate.puml
│   ├── AuroraOracleInstance.puml
│   ├── AuroraPIOPSInstance.puml
│   ├── AuroraPostgreSQLInstanceAlternate.puml
│   ├── AuroraPostgreSQLInstance.puml
│   ├── Aurora.puml
│   ├── AuroraSQLServerInstanceAlternate.puml
│   ├── AuroraSQLServerInstance.puml
│   ├── AuroraTrustedLanguageExtensionsforPostgreSQL.puml
│   ├── DatabaseMigrationServiceDatabasemigrationworkflowjob.puml
│   ├── DatabaseMigrationService.puml
│   ├── Database.puml
│   ├── DocumentDBElasticClusters.puml
│   ├── DocumentDB.puml
│   ├── DynamoDBAmazonDynamoDBAccelerator.puml
│   ├── DynamoDBAttribute.puml
│   ├── DynamoDBAttributes.puml
│   ├── DynamoDBGlobalsecondaryindex.puml
│   ├── DynamoDBItem.puml
│   ├── DynamoDBItems.puml
│   ├── DynamoDB.puml
│   ├── DynamoDBStandardAccessTableClass.puml
│   ├── DynamoDBStandardInfrequentAccessTableClass.puml
│   ├── DynamoDBStream.puml
│   ├── DynamoDBTable.puml
│   ├── ElastiCacheCacheNode.puml
│   ├── ElastiCacheElastiCacheforMemcached.puml
│   ├── ElastiCacheElastiCacheforRedis.puml
│   ├── ElastiCacheElastiCacheforValkey.puml
│   ├── ElastiCache.puml
│   ├── Keyspaces.puml
│   ├── MemoryDB.puml
│   ├── Neptune.puml
│   ├── OracleDatabaseatAWS.puml
│   ├── RDSBlueGreenDeployments.puml
│   ├── RDSMultiAZDBCluster.puml
│   ├── RDSMultiAZ.puml
│   ├── RDSOptimizedWrites.puml
│   ├── RDSProxyInstanceAlternate.puml
│   ├── RDSProxyInstance.puml
│   ├── RDS.puml
│   ├── RDSTrustedLanguageExtensionsforPostgreSQL.puml
│   └── Timestream.puml
├── DeveloperTools
│   ├── all.puml
│   ├── Cloud9Cloud9.puml
│   ├── Cloud9.puml
│   ├── CloudControlAPI.puml
│   ├── CloudDevelopmentKit.puml
│   ├── CloudShell.puml
│   ├── CodeArtifact.puml
│   ├── CodeBuild.puml
│   ├── CodeCatalyst.puml
│   ├── CodeCommit.puml
│   ├── CodeDeploy.puml
│   ├── CodePipeline.puml
│   ├── CommandLineInterface.puml
│   ├── Corretto.puml
│   ├── DeveloperTools.puml
│   ├── FaultInjectionService.puml
│   ├── InfrastructureComposer.puml
│   ├── ToolsandSDKs.puml
│   └── XRay.puml
├── EndUserComputing
│   ├── all.puml
│   ├── EndUserComputing.puml
│   └── WorkSpaces.puml
├── FrontEndWebMobile
│   ├── all.puml
│   ├── AmplifyAWSAmplifyStudio.puml
│   ├── Amplify.puml
│   ├── DeviceFarm.puml
│   ├── FrontEndWebMobile.puml
│   ├── LocationServiceGeofence.puml
│   ├── LocationServiceMap.puml
│   ├── LocationServicePlace.puml
│   ├── LocationService.puml
│   ├── LocationServiceRoutes.puml
│   └── LocationServiceTrack.puml
├── Games
│   ├── all.puml
│   ├── GameLiftServers.puml
│   ├── GameLiftStreams.puml
│   ├── Games.puml
│   └── Open3DEngine.puml
├── General
│   ├── Alert.puml
│   ├── all.puml
│   ├── AuthenticatedUser.puml
│   ├── AWSManagementConsole.puml
│   ├── Camera.puml
│   ├── Chat.puml
│   ├── Client.puml
│   ├── ColdStorage.puml
│   ├── Credentials.puml
│   ├── DataStream.puml
│   ├── DataTable.puml
│   ├── Disk.puml
│   ├── Document.puml
│   ├── Documents.puml
│   ├── Email.puml
│   ├── Firewall.puml
│   ├── Folder.puml
│   ├── Folders.puml
│   ├── Forums.puml
│   ├── Gear.puml
│   ├── GenericApplication.puml
│   ├── Genericdatabase.puml
│   ├── GitRepository.puml
│   ├── Globe.puml
│   ├── Internetalt1.puml
│   ├── Internetalt2.puml
│   ├── Internet.puml
│   ├── JSONScript.puml
│   ├── Logs.puml
│   ├── MagnifyingGlass.puml
│   ├── Marketplace.puml
│   ├── Metrics.puml
│   ├── Mobileclient.puml
│   ├── Multimedia.puml
│   ├── Officebuilding.puml
│   ├── ProgrammingLanguage.puml
│   ├── Question.puml
│   ├── Recover.puml
│   ├── SAMLtoken.puml
│   ├── SDK.puml
│   ├── Servers.puml
│   ├── Shield2.puml
│   ├── SourceCode.puml
│   ├── SSLpadlock.puml
│   ├── Tapestorage.puml
│   ├── Toolkit.puml
│   ├── Traditionalserver.puml
│   ├── User.puml
│   └── Users.puml
├── Groups
│   ├── all.puml
│   ├── AutoScalingGroup.puml
│   ├── AvailabilityZone.puml
│   ├── AWSAccount.puml
│   ├── AWSCloudAlt.puml
│   ├── AWSCloud.puml
│   ├── CorporateDataCenter.puml
│   ├── EC2InstanceContents.puml
│   ├── ElasticBeanstalkContainer.puml
│   ├── GenericAlt.puml
│   ├── GenericBlue.puml
│   ├── GenericGreen.puml
│   ├── GenericOrange.puml
│   ├── GenericPink.puml
│   ├── Generic.puml
│   ├── GenericPurple.puml
│   ├── GenericRed.puml
│   ├── GenericTurquoise.puml
│   ├── IoTGreengrassDeployment.puml
│   ├── IoTGreengrass.puml
│   ├── PrivateSubnet.puml
│   ├── PublicSubnet.puml
│   ├── Region.puml
│   ├── SecurityGroup.puml
│   ├── ServerContents.puml
│   ├── SpotFleet.puml
│   ├── StepFunctionsWorkflow.puml
│   └── VPC.puml
├── InternetOfThings
│   ├── all.puml
│   ├── FreeRTOS.puml
│   ├── InternetOfThings.puml
│   ├── IoTAction.puml
│   ├── IoTActuator.puml
│   ├── IoTAlexaEnabledDevice.puml
│   ├── IoTAlexaSkill.puml
│   ├── IoTAlexaVoiceService.puml
│   ├── IoTCertificate.puml
│   ├── IoTCoreDeviceAdvisor.puml
│   ├── IoTCoreDeviceLocation.puml
│   ├── IoTCore.puml
│   ├── IoTDesiredState.puml
│   ├── IoTDeviceDefenderIoTDeviceJobs.puml
│   ├── IoTDeviceDefender.puml
│   ├── IoTDeviceGateway.puml
│   ├── IoTDeviceManagementFleetHub.puml
│   ├── IoTDeviceManagement.puml
│   ├── IoTDeviceTester.puml
│   ├── IoTEcho.puml
│   ├── IoTEvents.puml
│   ├── IoTExpressLink.puml
│   ├── IoTFireTV.puml
│   ├── IoTFireTVStick.puml
│   ├── IoTFleetWise.puml
│   ├── IoTGreengrassArtifact.puml
│   ├── IoTGreengrassComponentMachineLearning.puml
│   ├── IoTGreengrassComponentNucleus.puml
│   ├── IoTGreengrassComponentPrivate.puml
│   ├── IoTGreengrassComponentPublic.puml
│   ├── IoTGreengrassComponent.puml
│   ├── IoTGreengrassConnector.puml
│   ├── IoTGreengrassInterprocessCommunication.puml
│   ├── IoTGreengrassProtocol.puml
│   ├── IoTGreengrass.puml
│   ├── IoTGreengrassRecipe.puml
│   ├── IoTGreengrassStreamManager.puml
│   ├── IoTHardwareBoard.puml
│   ├── IoTHTTP2Protocol.puml
│   ├── IoTHTTPProtocol.puml
│   ├── IoTLambdaFunction.puml
│   ├── IoTLoRaWANProtocol.puml
│   ├── IoTMQTTProtocol.puml
│   ├── IoTOverAirUpdate.puml
│   ├── IoTPolicy.puml
│   ├── IoTReportedState.puml
│   ├── IoTRule.puml
│   ├── IoTSailboat.puml
│   ├── IoTSensor.puml
│   ├── IoTServo.puml
│   ├── IoTShadow.puml
│   ├── IoTSimulator.puml
│   ├── IoTSiteWiseAssetHierarchy.puml
│   ├── IoTSiteWiseAssetModel.puml
│   ├── IoTSiteWiseAssetProperties.puml
│   ├── IoTSiteWiseAsset.puml
│   ├── IoTSiteWiseDataStreams.puml
│   ├── IoTSiteWise.puml
│   ├── IoTThingBank.puml
│   ├── IoTThingBicycle.puml
│   ├── IoTThingCamera.puml
│   ├── IoTThingCar.puml
│   ├── IoTThingCart.puml
│   ├── IoTThingCoffeePot.puml
│   ├── IoTThingDoorLock.puml
│   ├── IoTThingFactory.puml
│   ├── IoTThingFreeRTOSDevice.puml
│   ├── IoTThingGeneric.puml
│   ├── IoTThingHouse.puml
│   ├── IoTThingHumiditySensor.puml
│   ├── IoTThingIndustrialPC.puml
│   ├── IoTThingLightbulb.puml
│   ├── IoTThingMedicalEmergency.puml
│   ├── IoTThingPLC.puml
│   ├── IoTThingPoliceEmergency.puml
│   ├── IoTThingRelay.puml
│   ├── IoTThingStacklight.puml
│   ├── IoTThingTemperatureHumiditySensor.puml
│   ├── IoTThingTemperatureSensor.puml
│   ├── IoTThingTemperatureVibrationSensor.puml
│   ├── IoTThingThermostat.puml
│   ├── IoTThingTravel.puml
│   ├── IoTThingUtility.puml
│   ├── IoTThingVibrationSensor.puml
│   ├── IoTThingWindfarm.puml
│   ├── IoTTopic.puml
│   └── IoTTwinMaker.puml
├── ManagementGovernance
│   ├── all.puml
│   ├── AppConfig.puml
│   ├── ApplicationAutoScaling2.puml
│   ├── AutoScaling.puml
│   ├── BackintAgent.puml
│   ├── Chatbot.puml
│   ├── CloudFormationChangeSet.puml
│   ├── CloudFormation.puml
│   ├── CloudFormationStack.puml
│   ├── CloudFormationTemplate.puml
│   ├── CloudTrailCloudTrailLake.puml
│   ├── CloudTrail.puml
│   ├── CloudWatchAlarm.puml
│   ├── CloudWatchCrossaccountObservability.puml
│   ├── CloudWatchDataProtection.puml
│   ├── CloudWatchEventEventBased.puml
│   ├── CloudWatchEventTimeBased.puml
│   ├── CloudWatchEvidently.puml
│   ├── CloudWatchLogs.puml
│   ├── CloudWatchMetricsInsights.puml
│   ├── CloudWatch.puml
│   ├── CloudWatchRule.puml
│   ├── CloudWatchRUM.puml
│   ├── CloudWatchSynthetics.puml
│   ├── ComputeOptimizer.puml
│   ├── Config.puml
│   ├── ConsoleMobileApplication.puml
│   ├── ControlTower.puml
│   ├── DevOpsAgent.puml
│   ├── DistroforOpenTelemetry.puml
│   ├── HealthDashboard.puml
│   ├── LaunchWizard.puml
│   ├── LicenseManagerApplicationDiscovery.puml
│   ├── LicenseManagerLicenseBlending.puml
│   ├── LicenseManager.puml
│   ├── ManagedGrafana.puml
│   ├── ManagedServiceforPrometheus.puml
│   ├── ManagementConsole.puml
│   ├── ManagementGovernance.puml
│   ├── OrganizationsAccount.puml
│   ├── OrganizationsManagementAccount.puml
│   ├── OrganizationsOrganizationalUnit.puml
│   ├── Organizations.puml
│   ├── PartnerCentral.puml
│   ├── Proton.puml
│   ├── ResilienceHub.puml
│   ├── ResourceExplorer.puml
│   ├── ServiceCatalog.puml
│   ├── ServiceManagementConnector.puml
│   ├── SystemsManagerApplicationManager.puml
│   ├── SystemsManagerAutomation.puml
│   ├── SystemsManagerChangeCalendar.puml
│   ├── SystemsManagerChangeManager.puml
│   ├── SystemsManagerCompliance.puml
│   ├── SystemsManagerDistributor.puml
│   ├── SystemsManagerDocuments.puml
│   ├── SystemsManagerIncidentManager.puml
│   ├── SystemsManagerInventory.puml
│   ├── SystemsManagerMaintenanceWindows.puml
│   ├── SystemsManagerOpsCenter.puml
│   ├── SystemsManagerParameterStore.puml
│   ├── SystemsManagerPatchManager.puml
│   ├── SystemsManager.puml
│   ├── SystemsManagerRunCommand.puml
│   ├── SystemsManagerSessionManager.puml
│   ├── SystemsManagerStateManager.puml
│   ├── TelcoNetworkBuilder.puml
│   ├── TrustedAdvisorChecklistCost.puml
│   ├── TrustedAdvisorChecklistFaultTolerant.puml
│   ├── TrustedAdvisorChecklistPerformance.puml
│   ├── TrustedAdvisorChecklist.puml
│   ├── TrustedAdvisorChecklistSecurity.puml
│   ├── TrustedAdvisor.puml
│   ├── UserNotifications.puml
│   └── WellArchitectedTool.puml
├── MediaServices
│   ├── all.puml
│   ├── CloudDigitalInterface.puml
│   ├── DeadlineCloud.puml
│   ├── ElementalAppliancesSoftware.puml
│   ├── ElementalConductor.puml
│   ├── ElementalDelta.puml
│   ├── ElementalLink.puml
│   ├── ElementalLive.puml
│   ├── ElementalMediaConnectMediaConnectGateway.puml
│   ├── ElementalMediaConnect.puml
│   ├── ElementalMediaConvert.puml
│   ├── ElementalMediaLive.puml
│   ├── ElementalMediaPackage.puml
│   ├── ElementalMediaStore.puml
│   ├── ElementalMediaTailor.puml
│   ├── ElementalServer.puml
│   ├── InteractiveVideoService.puml
│   ├── KinesisVideoStreams2.puml
│   ├── MediaServices.puml
│   ├── ThinkboxDeadline.puml
│   ├── ThinkboxFrost.puml
│   ├── ThinkboxKrakatoa.puml
│   ├── ThinkboxStoke.puml
│   └── ThinkboxXMesh.puml
├── MigrationModernization
│   ├── all.puml
│   ├── ApplicationDiscoveryServiceAWSAgentlessCollector.puml
│   ├── ApplicationDiscoveryServiceAWSDiscoveryAgent.puml
│   ├── ApplicationDiscoveryServiceMigrationEvaluatorCollector.puml
│   ├── ApplicationDiscoveryService.puml
│   ├── ApplicationMigrationService.puml
│   ├── DatasyncAgent.puml
│   ├── DataSyncDiscovery.puml
│   ├── DataSync.puml
│   ├── DataTransferTerminal.puml
│   ├── MainframeModernizationAnalyzer.puml
│   ├── MainframeModernizationCompiler.puml
│   ├── MainframeModernizationConverter.puml
│   ├── MainframeModernizationDeveloper.puml
│   ├── MainframeModernization.puml
│   ├── MainframeModernizationRuntime.puml
│   ├── MigrationEvaluator.puml
│   ├── MigrationHub.puml
│   ├── MigrationHubRefactorSpacesApplications.puml
│   ├── MigrationHubRefactorSpacesEnvironments.puml
│   ├── MigrationHubRefactorSpacesServices.puml
│   ├── MigrationModernization.puml
│   ├── TransferFamilyAWSAS2.puml
│   ├── TransferFamilyAWSFTP.puml
│   ├── TransferFamilyAWSFTPS.puml
│   ├── TransferFamilyAWSSFTP.puml
│   ├── TransferFamily.puml
│   └── Transform.puml
├── MulticloudandHybrid
│   ├── all.puml
│   └── MulticloudandHybrid.puml
├── NetworkingContentDelivery
│   ├── all.puml
│   ├── APIGatewayEndpoint.puml
│   ├── APIGateway.puml
│   ├── ApplicationRecoveryController.puml
│   ├── AppMeshMesh.puml
│   ├── AppMesh.puml
│   ├── AppMeshVirtualGateway.puml
│   ├── AppMeshVirtualNode.puml
│   ├── AppMeshVirtualRouter.puml
│   ├── AppMeshVirtualService.puml
│   ├── ClientVPN.puml
│   ├── CloudFrontDownloadDistribution.puml
│   ├── CloudFrontEdgeLocation.puml
│   ├── CloudFrontFunctions.puml
│   ├── CloudFront.puml
│   ├── CloudFrontStreamingDistribution.puml
│   ├── CloudMapNamespace.puml
│   ├── CloudMap.puml
│   ├── CloudMapResource.puml
│   ├── CloudMapService.puml
│   ├── CloudWANCoreNetworkEdge.puml
│   ├── CloudWAN.puml
│   ├── CloudWANSegmentNetwork.puml
│   ├── CloudWANTransitGatewayRouteTableAttachment.puml
│   ├── DirectConnectGateway.puml
│   ├── DirectConnect.puml
│   ├── ElasticLoadBalancingApplicationLoadBalancer.puml
│   ├── ElasticLoadBalancingClassicLoadBalancer.puml
│   ├── ElasticLoadBalancingGatewayLoadBalancer.puml
│   ├── ElasticLoadBalancingNetworkLoadBalancer.puml
│   ├── ElasticLoadBalancing.puml
│   ├── GlobalAccelerator.puml
│   ├── NetworkingContentDelivery.puml
│   ├── PrivateLink.puml
│   ├── Route53HostedZone.puml
│   ├── Route53.puml
│   ├── Route53ReadinessChecks.puml
│   ├── Route53ResolverDNSFirewall.puml
│   ├── Route53Resolver.puml
│   ├── Route53ResolverQueryLogging.puml
│   ├── Route53RouteTable.puml
│   ├── Route53RoutingControls.puml
│   ├── RTBFabric.puml
│   ├── SitetoSiteVPN.puml
│   ├── TransitGatewayAttachment.puml
│   ├── TransitGateway.puml
│   ├── VerifiedAccess.puml
│   ├── VirtualPrivateCloud.puml
│   ├── VPCCarrierGateway.puml
│   ├── VPCCustomerGateway.puml
│   ├── VPCElasticNetworkAdapter.puml
│   ├── VPCElasticNetworkInterface.puml
│   ├── VPCEndpoints.puml
│   ├── VPCFlowLogs.puml
│   ├── VPCInternetGateway.puml
│   ├── VPCLattice.puml
│   ├── VPCNATGateway.puml
│   ├── VPCNetworkAccessAnalyzer.puml
│   ├── VPCNetworkAccessControlList.puml
│   ├── VPCPeeringConnection.puml
│   ├── VPCReachabilityAnalyzer.puml
│   ├── VPCRouter.puml
│   ├── VPCTrafficMirroring.puml
│   ├── VPCVirtualprivatecloudVPC.puml
│   ├── VPCVPNConnection.puml
│   └── VPCVPNGateway.puml
├── QuantumTechnologies
│   ├── all.puml
│   ├── BraketChandelier.puml
│   ├── BraketChip.puml
│   ├── BraketEmbeddedSimulator.puml
│   ├── BraketManagedSimulator.puml
│   ├── BraketNoiseSimulator.puml
│   ├── Braket.puml
│   ├── BraketQPU.puml
│   ├── BraketSimulator1.puml
│   ├── BraketSimulator2.puml
│   ├── BraketSimulator3.puml
│   ├── BraketSimulator4.puml
│   ├── BraketSimulator.puml
│   ├── BraketStateVector.puml
│   ├── BraketTensorNetwork.puml
│   └── QuantumTechnologies.puml
├── Satellite
│   ├── all.puml
│   ├── GroundStation.puml
│   └── Satellite.puml
├── SecurityIdentityCompliance
│   ├── all.puml
│   ├── Artifact.puml
│   ├── AuditManager.puml
│   ├── CertificateManagerCertificateAuthority.puml
│   ├── CertificateManager.puml
│   ├── CloudDirectory.puml
│   ├── CloudHSM.puml
│   ├── Cognito.puml
│   ├── Detective.puml
│   ├── DirectoryServiceADConnector.puml
│   ├── DirectoryServiceAWSManagedMicrosoftAD.puml
│   ├── DirectoryService.puml
│   ├── DirectoryServiceSimpleAD.puml
│   ├── FirewallManager.puml
│   ├── GuardDuty.puml
│   ├── IAMIdentityCenter.puml
│   ├── IdentityAccessManagementAddon.puml
│   ├── IdentityAccessManagementAWSSTSAlternate.puml
│   ├── IdentityAccessManagementAWSSTS.puml
│   ├── IdentityAccessManagementDataEncryptionKey.puml
│   ├── IdentityAccessManagementEncryptedData.puml
│   ├── IdentityAccessManagementIAMAccessAnalyzer.puml
│   ├── IdentityAccessManagementIAMRolesAnywhere.puml
│   ├── IdentityAccessManagementLongTermSecurityCredential.puml
│   ├── IdentityAccessManagementMFAToken.puml
│   ├── IdentityAccessManagementPermissions.puml
│   ├── IdentityAccessManagementRole.puml
│   ├── IdentityAccessManagementTemporarySecurityCredential.puml
│   ├── IdentityandAccessManagement.puml
│   ├── InspectorAgent.puml
│   ├── Inspector.puml
│   ├── KeyManagementServiceExternalKeyStore.puml
│   ├── KeyManagementService.puml
│   ├── Macie.puml
│   ├── NetworkFirewallEndpoints.puml
│   ├── NetworkFirewall.puml
│   ├── PaymentCryptography.puml
│   ├── PrivateCertificateAuthority.puml
│   ├── ResourceAccessManager.puml
│   ├── SecretsManager.puml
│   ├── SecurityAgent.puml
│   ├── SecurityHubFinding.puml
│   ├── SecurityHub.puml
│   ├── SecurityIdentityCompliance.puml
│   ├── SecurityIncidentResponse.puml
│   ├── SecurityLake.puml
│   ├── ShieldAWSShieldAdvanced.puml
│   ├── Shield.puml
│   ├── Signer.puml
│   ├── VerifiedPermissions.puml
│   ├── WAFBadBot.puml
│   ├── WAFBotControl.puml
│   ├── WAFBot.puml
│   ├── WAFFilteringRule.puml
│   ├── WAFLabels.puml
│   ├── WAFManagedRule.puml
│   ├── WAF.puml
│   └── WAFRule.puml
├── Serverless
│   ├── all.puml
│   └── Serverless.puml
└── Storage
    ├── all.puml
    ├── BackupAuditManager.puml
    ├── BackupAWSBackupforAWSCloudFormation.puml
    ├── BackupAWSBackupsupportforAmazonFSxforNetAppONTAP.puml
    ├── BackupAWSBackupsupportforAmazonS3.puml
    ├── BackupAWSBackupsupportforVMwareWorkloads.puml
    ├── BackupBackupPlan.puml
    ├── BackupBackupRestore.puml
    ├── BackupBackupVault.puml
    ├── BackupComplianceReporting.puml
    ├── BackupCompute.puml
    ├── BackupDatabase.puml
    ├── BackupGateway.puml
    ├── BackupLegalHold.puml
    ├── Backup.puml
    ├── BackupRecoveryPointObjective.puml
    ├── BackupRecoveryTimeObjective.puml
    ├── BackupStorage.puml
    ├── BackupVaultLock.puml
    ├── BackupVirtualMachineMonitor.puml
    ├── BackupVirtualMachine.puml
    ├── EFS.puml
    ├── ElasticBlockStoreAmazonDataLifecycleManager.puml
    ├── ElasticBlockStoreMultipleVolumes.puml
    ├── ElasticBlockStore.puml
    ├── ElasticBlockStoreSnapshot.puml
    ├── ElasticBlockStoreVolumegp3.puml
    ├── ElasticBlockStoreVolume.puml
    ├── ElasticDisasterRecovery.puml
    ├── ElasticFileSystemElasticThroughput.puml
    ├── ElasticFileSystemFileSystem.puml
    ├── ElasticFileSystemIntelligentTiering.puml
    ├── ElasticFileSystemOneZoneInfrequentAccess.puml
    ├── ElasticFileSystemOneZone.puml
    ├── ElasticFileSystemStandardInfrequentAccess.puml
    ├── ElasticFileSystemStandard.puml
    ├── FileCacheHybridNFSlinkeddatasets.puml
    ├── FileCacheOnpremisesNFSlinkeddatasets.puml
    ├── FileCache.puml
    ├── FileCacheS3linkeddatasets.puml
    ├── FSxforLustre.puml
    ├── FSxforNetAppONTAP.puml
    ├── FSxforOpenZFS.puml
    ├── FSxforWFS.puml
    ├── FSx.puml
    ├── S3onOutposts.puml
    ├── SimpleStorageServiceBucket.puml
    ├── SimpleStorageServiceBucketWithObjects.puml
    ├── SimpleStorageServiceDirectoryBucket.puml
    ├── SimpleStorageServiceGeneralAccessPoints.puml
    ├── SimpleStorageServiceGlacierArchive.puml
    ├── SimpleStorageServiceGlacier.puml
    ├── SimpleStorageServiceGlacierVault.puml
    ├── SimpleStorageServiceObject.puml
    ├── SimpleStorageService.puml
    ├── SimpleStorageServiceS3BatchOperations.puml
    ├── SimpleStorageServiceS3ExpressOneZone.puml
    ├── SimpleStorageServiceS3GlacierDeepArchive.puml
    ├── SimpleStorageServiceS3GlacierFlexibleRetrieval.puml
    ├── SimpleStorageServiceS3GlacierInstantRetrieval.puml
    ├── SimpleStorageServiceS3IntelligentTiering.puml
    ├── SimpleStorageServiceS3MultiRegionAccessPoints.puml
    ├── SimpleStorageServiceS3ObjectLambdaAccessPoints.puml
    ├── SimpleStorageServiceS3ObjectLambda.puml
    ├── SimpleStorageServiceS3ObjectLock.puml
    ├── SimpleStorageServiceS3OneZoneIA.puml
    ├── SimpleStorageServiceS3OnOutposts.puml
    ├── SimpleStorageServiceS3Replication.puml
    ├── SimpleStorageServiceS3ReplicationTimeControl.puml
    ├── SimpleStorageServiceS3Select.puml
    ├── SimpleStorageServiceS3StandardIA.puml
    ├── SimpleStorageServiceS3Standard.puml
    ├── SimpleStorageServiceS3StorageLens.puml
    ├── SimpleStorageServiceS3Tables.puml
    ├── SimpleStorageServiceS3Vectors.puml
    ├── SimpleStorageServiceVPCAccessPoints.puml
    ├── SnowballEdge.puml
    ├── Snowball.puml
    ├── SnowballSnowballImportExport.puml
    ├── StorageGatewayAmazonFSxFileGateway.puml
    ├── StorageGatewayAmazonS3FileGateway.puml
    ├── StorageGatewayCachedVolume.puml
    ├── StorageGatewayFileGateway.puml
    ├── StorageGatewayNoncachedVolume.puml
    ├── StorageGateway.puml
    ├── StorageGatewayTapeGateway.puml
    ├── StorageGatewayVirtualTapeLibrary.puml
    ├── StorageGatewayVolumeGateway.puml
    └── Storage.puml

### Examples

#### Hello world

@startuml Hello World
' Uncomment the line below for "dark mode" styling
'!$AWS_DARK = true

!define AWSPuml https://raw.githubusercontent.com/awslabs/aws-icons-for-plantuml/v23.0/dist
!include AWSPuml/AWSCommon.puml
!include AWSPuml/BusinessApplications/all.puml
!include AWSPuml/Storage/SimpleStorageService.puml

actor "Person" as personAlias
WorkDocs(desktopAlias, "Label", "Technology", "Optional Description")
SimpleStorageService(storageAlias, "Label", "Technology", "Optional Description")

personAlias --> desktopAlias
desktopAlias --> storageAlias

@enduml

#### Sequence diagrams

@startuml Sequence Diagram - Technical
' Uncomment the line below for "dark mode" styling
'!$AWS_DARK = true

!define AWSPuml https://raw.githubusercontent.com/awslabs/aws-icons-for-plantuml/v23.0/dist
!include AWSPuml/AWSCommon.puml
!include AWSPuml/Compute/all.puml
!include AWSPuml/NetworkingContentDelivery/APIGateway.puml
!include AWSPuml/General/Internetalt1.puml
!include AWSPuml/Database/DynamoDB.puml

actor User as user
APIGatewayParticipant(api, Credit Card System, All methods are POST)
LambdaParticipant(lambda,AuthorizeCard,)
DynamoDBParticipant(db, PaymentTransactions, sortkey=transaction_id+token)
Internetalt1Participant(processor, Authorizer, Returns status and token)

user -> api: Process transaction\nPOST /prod/process
api -> lambda: Invokes lambda with cardholder details
lambda -> processor: Submit via API token\ncard number, expiry, CID
processor -> processor: Validate and create token
processor -> lambda: Returns status code and token
lambda -> db: PUT transaction id, token
lambda -> api: Returns\nstatus code, transaction id
api -> user: Returns status code
@enduml

#### Groups

@startuml VPC
' Uncomment the line below for "dark mode" styling
'!$AWS_DARK = true

!define AWSPuml https://raw.githubusercontent.com/awslabs/aws-icons-for-plantuml/v23.0/dist
!include AWSPuml/AWSCommon.puml
!include AWSPuml/AWSSimplified.puml
!include AWSPuml/Compute/EC2.puml
!include AWSPuml/Compute/EC2Instance.puml
!include AWSPuml/Groups/AWSCloud.puml
!include AWSPuml/Groups/VPC.puml
!include AWSPuml/Groups/AvailabilityZone.puml
!include AWSPuml/Groups/PublicSubnet.puml
!include AWSPuml/Groups/PrivateSubnet.puml
!include AWSPuml/NetworkingContentDelivery/VPCNATGateway.puml
!include AWSPuml/NetworkingContentDelivery/VPCInternetGateway.puml

hide stereotype
skinparam linetype ortho

AWSCloudGroup(cloud) {
  VPCGroup(vpc) {
    VPCInternetGateway(internet_gateway, "Internet gateway", "")

    AvailabilityZoneGroup(az_1, "\tAvailability Zone 1\t") {
      PublicSubnetGroup(az_1_public, "Public subnet") {
        VPCNATGateway(az_1_nat_gateway, "NAT gateway", "") #Transparent
      }
      PrivateSubnetGroup(az_1_private, "Private subnet") {
        EC2Instance(az_1_ec2_1, "Instance", "") #Transparent
      }

      az_1_ec2_1 .u.> az_1_nat_gateway
    }

    AvailabilityZoneGroup(az_2, "\tAvailability Zone 2\t") {
      PublicSubnetGroup(az_2_public, "Public subnet") {
        VPCNATGateway(az_2_nat_gateway, "NAT gateway", "") #Transparent
      }
      PrivateSubnetGroup(az_2_private, "Private subnet") {
        EC2Instance(az_2_ec2_1, "Instance", "") #Transparent
      }

      az_2_ec2_1 .u.> az_2_nat_gateway
    }

    az_2_nat_gateway .[hidden]u.> internet_gateway
    az_1_nat_gateway .[hidden]u.> internet_gateway
  }
}
@enduml

### Build the diagrams

To build the diagrams use the plantuml.sh script.
