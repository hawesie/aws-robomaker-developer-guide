# StartSimulationJobBatch<a name="API_StartSimulationJobBatch"></a>

Starts a new simulation job batch\. The batch is defined using one or more `SimulationJobRequest` objects\. 

## Request Syntax<a name="API_StartSimulationJobBatch_RequestSyntax"></a>

```
POST /startSimulationJobBatch HTTP/1.1
Content-type: application/json

{
   "[batchPolicy](#robomaker-StartSimulationJobBatch-request-batchPolicy)": { 
      "[maxConcurrency](API_BatchPolicy.md#robomaker-Type-BatchPolicy-maxConcurrency)": number,
      "[timeoutInSeconds](API_BatchPolicy.md#robomaker-Type-BatchPolicy-timeoutInSeconds)": number
   },
   "[clientRequestToken](#robomaker-StartSimulationJobBatch-request-clientRequestToken)": "string",
   "[createSimulationJobRequests](#robomaker-StartSimulationJobBatch-request-createSimulationJobRequests)": [ 
      { 
         "[dataSources](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-dataSources)": [ 
            { 
               "[name](API_DataSourceConfig.md#robomaker-Type-DataSourceConfig-name)": "string",
               "[s3Bucket](API_DataSourceConfig.md#robomaker-Type-DataSourceConfig-s3Bucket)": "string",
               "[s3Keys](API_DataSourceConfig.md#robomaker-Type-DataSourceConfig-s3Keys)": [ "string" ]
            }
         ],
         "[failureBehavior](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-failureBehavior)": "string",
         "[iamRole](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-iamRole)": "string",
         "[loggingConfig](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-loggingConfig)": { 
            "[recordAllRosTopics](API_LoggingConfig.md#robomaker-Type-LoggingConfig-recordAllRosTopics)": boolean
         },
         "[maxJobDurationInSeconds](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-maxJobDurationInSeconds)": number,
         "[outputLocation](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-outputLocation)": { 
            "[s3Bucket](API_OutputLocation.md#robomaker-Type-OutputLocation-s3Bucket)": "string",
            "[s3Prefix](API_OutputLocation.md#robomaker-Type-OutputLocation-s3Prefix)": "string"
         },
         "[robotApplications](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-robotApplications)": [ 
            { 
               "[application](API_RobotApplicationConfig.md#robomaker-Type-RobotApplicationConfig-application)": "string",
               "[applicationVersion](API_RobotApplicationConfig.md#robomaker-Type-RobotApplicationConfig-applicationVersion)": "string",
               "[launchConfig](API_RobotApplicationConfig.md#robomaker-Type-RobotApplicationConfig-launchConfig)": { 
                  "[environmentVariables](API_LaunchConfig.md#robomaker-Type-LaunchConfig-environmentVariables)": { 
                     "string" : "string" 
                  },
                  "[launchFile](API_LaunchConfig.md#robomaker-Type-LaunchConfig-launchFile)": "string",
                  "[packageName](API_LaunchConfig.md#robomaker-Type-LaunchConfig-packageName)": "string",
                  "[portForwardingConfig](API_LaunchConfig.md#robomaker-Type-LaunchConfig-portForwardingConfig)": { 
                     "[portMappings](API_PortForwardingConfig.md#robomaker-Type-PortForwardingConfig-portMappings)": [ 
                        { 
                           "[applicationPort](API_PortMapping.md#robomaker-Type-PortMapping-applicationPort)": number,
                           "[enableOnPublicIp](API_PortMapping.md#robomaker-Type-PortMapping-enableOnPublicIp)": boolean,
                           "[jobPort](API_PortMapping.md#robomaker-Type-PortMapping-jobPort)": number
                        }
                     ]
                  }
               }
            }
         ],
         "[simulationApplications](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-simulationApplications)": [ 
            { 
               "[application](API_SimulationApplicationConfig.md#robomaker-Type-SimulationApplicationConfig-application)": "string",
               "[applicationVersion](API_SimulationApplicationConfig.md#robomaker-Type-SimulationApplicationConfig-applicationVersion)": "string",
               "[launchConfig](API_SimulationApplicationConfig.md#robomaker-Type-SimulationApplicationConfig-launchConfig)": { 
                  "[environmentVariables](API_LaunchConfig.md#robomaker-Type-LaunchConfig-environmentVariables)": { 
                     "string" : "string" 
                  },
                  "[launchFile](API_LaunchConfig.md#robomaker-Type-LaunchConfig-launchFile)": "string",
                  "[packageName](API_LaunchConfig.md#robomaker-Type-LaunchConfig-packageName)": "string",
                  "[portForwardingConfig](API_LaunchConfig.md#robomaker-Type-LaunchConfig-portForwardingConfig)": { 
                     "[portMappings](API_PortForwardingConfig.md#robomaker-Type-PortForwardingConfig-portMappings)": [ 
                        { 
                           "[applicationPort](API_PortMapping.md#robomaker-Type-PortMapping-applicationPort)": number,
                           "[enableOnPublicIp](API_PortMapping.md#robomaker-Type-PortMapping-enableOnPublicIp)": boolean,
                           "[jobPort](API_PortMapping.md#robomaker-Type-PortMapping-jobPort)": number
                        }
                     ]
                  }
               }
            }
         ],
         "[tags](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-tags)": { 
            "string" : "string" 
         },
         "[useDefaultApplications](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-useDefaultApplications)": boolean,
         "[vpcConfig](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-vpcConfig)": { 
            "[assignPublicIp](API_VPCConfig.md#robomaker-Type-VPCConfig-assignPublicIp)": boolean,
            "[securityGroups](API_VPCConfig.md#robomaker-Type-VPCConfig-securityGroups)": [ "string" ],
            "[subnets](API_VPCConfig.md#robomaker-Type-VPCConfig-subnets)": [ "string" ]
         }
      }
   ],
   "[tags](#robomaker-StartSimulationJobBatch-request-tags)": { 
      "string" : "string" 
   }
}
```

## URI Request Parameters<a name="API_StartSimulationJobBatch_RequestParameters"></a>

The request does not use any URI parameters\.

## Request Body<a name="API_StartSimulationJobBatch_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [batchPolicy](#API_StartSimulationJobBatch_RequestSyntax) **   <a name="robomaker-StartSimulationJobBatch-request-batchPolicy"></a>
The batch policy\.  
Type: [BatchPolicy](API_BatchPolicy.md) object  
Required: No

 ** [clientRequestToken](#API_StartSimulationJobBatch_RequestSyntax) **   <a name="robomaker-StartSimulationJobBatch-request-clientRequestToken"></a>
Unique, case\-sensitive identifier that you provide to ensure the idempotency of the request\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 64\.  
Pattern: `[a-zA-Z0-9_\-=]*`   
Required: No

 ** [createSimulationJobRequests](#API_StartSimulationJobBatch_RequestSyntax) **   <a name="robomaker-StartSimulationJobBatch-request-createSimulationJobRequests"></a>
A list of simulation job requests to create in the batch\.  
Type: Array of [SimulationJobRequest](API_SimulationJobRequest.md) objects  
Array Members: Minimum number of 1 item\.  
Required: Yes

 ** [tags](#API_StartSimulationJobBatch_RequestSyntax) **   <a name="robomaker-StartSimulationJobBatch-request-tags"></a>
A map that contains tag keys and tag values that are attached to the deployment job batch\.  
Type: String to string map  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Key Pattern: `[a-zA-Z0-9 _.\-\/+=:]*`   
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.  
Value Pattern: `[a-zA-Z0-9 _.\-\/+=:]*`   
Required: No

## Response Syntax<a name="API_StartSimulationJobBatch_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "[arn](#robomaker-StartSimulationJobBatch-response-arn)": "string",
   "[batchPolicy](#robomaker-StartSimulationJobBatch-response-batchPolicy)": { 
      "[maxConcurrency](API_BatchPolicy.md#robomaker-Type-BatchPolicy-maxConcurrency)": number,
      "[timeoutInSeconds](API_BatchPolicy.md#robomaker-Type-BatchPolicy-timeoutInSeconds)": number
   },
   "[clientRequestToken](#robomaker-StartSimulationJobBatch-response-clientRequestToken)": "string",
   "[createdAt](#robomaker-StartSimulationJobBatch-response-createdAt)": number,
   "[createdRequests](#robomaker-StartSimulationJobBatch-response-createdRequests)": [ 
      { 
         "[arn](API_SimulationJobSummary.md#robomaker-Type-SimulationJobSummary-arn)": "string",
         "[dataSourceNames](API_SimulationJobSummary.md#robomaker-Type-SimulationJobSummary-dataSourceNames)": [ "string" ],
         "[lastUpdatedAt](API_SimulationJobSummary.md#robomaker-Type-SimulationJobSummary-lastUpdatedAt)": number,
         "[name](API_SimulationJobSummary.md#robomaker-Type-SimulationJobSummary-name)": "string",
         "[robotApplicationNames](API_SimulationJobSummary.md#robomaker-Type-SimulationJobSummary-robotApplicationNames)": [ "string" ],
         "[simulationApplicationNames](API_SimulationJobSummary.md#robomaker-Type-SimulationJobSummary-simulationApplicationNames)": [ "string" ],
         "[status](API_SimulationJobSummary.md#robomaker-Type-SimulationJobSummary-status)": "string"
      }
   ],
   "[failedRequests](#robomaker-StartSimulationJobBatch-response-failedRequests)": [ 
      { 
         "[failedAt](API_FailedCreateSimulationJobRequest.md#robomaker-Type-FailedCreateSimulationJobRequest-failedAt)": number,
         "[failureCode](API_FailedCreateSimulationJobRequest.md#robomaker-Type-FailedCreateSimulationJobRequest-failureCode)": "string",
         "[failureReason](API_FailedCreateSimulationJobRequest.md#robomaker-Type-FailedCreateSimulationJobRequest-failureReason)": "string",
         "[request](API_FailedCreateSimulationJobRequest.md#robomaker-Type-FailedCreateSimulationJobRequest-request)": { 
            "[dataSources](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-dataSources)": [ 
               { 
                  "[name](API_DataSourceConfig.md#robomaker-Type-DataSourceConfig-name)": "string",
                  "[s3Bucket](API_DataSourceConfig.md#robomaker-Type-DataSourceConfig-s3Bucket)": "string",
                  "[s3Keys](API_DataSourceConfig.md#robomaker-Type-DataSourceConfig-s3Keys)": [ "string" ]
               }
            ],
            "[failureBehavior](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-failureBehavior)": "string",
            "[iamRole](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-iamRole)": "string",
            "[loggingConfig](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-loggingConfig)": { 
               "[recordAllRosTopics](API_LoggingConfig.md#robomaker-Type-LoggingConfig-recordAllRosTopics)": boolean
            },
            "[maxJobDurationInSeconds](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-maxJobDurationInSeconds)": number,
            "[outputLocation](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-outputLocation)": { 
               "[s3Bucket](API_OutputLocation.md#robomaker-Type-OutputLocation-s3Bucket)": "string",
               "[s3Prefix](API_OutputLocation.md#robomaker-Type-OutputLocation-s3Prefix)": "string"
            },
            "[robotApplications](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-robotApplications)": [ 
               { 
                  "[application](API_RobotApplicationConfig.md#robomaker-Type-RobotApplicationConfig-application)": "string",
                  "[applicationVersion](API_RobotApplicationConfig.md#robomaker-Type-RobotApplicationConfig-applicationVersion)": "string",
                  "[launchConfig](API_RobotApplicationConfig.md#robomaker-Type-RobotApplicationConfig-launchConfig)": { 
                     "[environmentVariables](API_LaunchConfig.md#robomaker-Type-LaunchConfig-environmentVariables)": { 
                        "string" : "string" 
                     },
                     "[launchFile](API_LaunchConfig.md#robomaker-Type-LaunchConfig-launchFile)": "string",
                     "[packageName](API_LaunchConfig.md#robomaker-Type-LaunchConfig-packageName)": "string",
                     "[portForwardingConfig](API_LaunchConfig.md#robomaker-Type-LaunchConfig-portForwardingConfig)": { 
                        "[portMappings](API_PortForwardingConfig.md#robomaker-Type-PortForwardingConfig-portMappings)": [ 
                           { 
                              "[applicationPort](API_PortMapping.md#robomaker-Type-PortMapping-applicationPort)": number,
                              "[enableOnPublicIp](API_PortMapping.md#robomaker-Type-PortMapping-enableOnPublicIp)": boolean,
                              "[jobPort](API_PortMapping.md#robomaker-Type-PortMapping-jobPort)": number
                           }
                        ]
                     }
                  }
               }
            ],
            "[simulationApplications](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-simulationApplications)": [ 
               { 
                  "[application](API_SimulationApplicationConfig.md#robomaker-Type-SimulationApplicationConfig-application)": "string",
                  "[applicationVersion](API_SimulationApplicationConfig.md#robomaker-Type-SimulationApplicationConfig-applicationVersion)": "string",
                  "[launchConfig](API_SimulationApplicationConfig.md#robomaker-Type-SimulationApplicationConfig-launchConfig)": { 
                     "[environmentVariables](API_LaunchConfig.md#robomaker-Type-LaunchConfig-environmentVariables)": { 
                        "string" : "string" 
                     },
                     "[launchFile](API_LaunchConfig.md#robomaker-Type-LaunchConfig-launchFile)": "string",
                     "[packageName](API_LaunchConfig.md#robomaker-Type-LaunchConfig-packageName)": "string",
                     "[portForwardingConfig](API_LaunchConfig.md#robomaker-Type-LaunchConfig-portForwardingConfig)": { 
                        "[portMappings](API_PortForwardingConfig.md#robomaker-Type-PortForwardingConfig-portMappings)": [ 
                           { 
                              "[applicationPort](API_PortMapping.md#robomaker-Type-PortMapping-applicationPort)": number,
                              "[enableOnPublicIp](API_PortMapping.md#robomaker-Type-PortMapping-enableOnPublicIp)": boolean,
                              "[jobPort](API_PortMapping.md#robomaker-Type-PortMapping-jobPort)": number
                           }
                        ]
                     }
                  }
               }
            ],
            "[tags](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-tags)": { 
               "string" : "string" 
            },
            "[useDefaultApplications](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-useDefaultApplications)": boolean,
            "[vpcConfig](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-vpcConfig)": { 
               "[assignPublicIp](API_VPCConfig.md#robomaker-Type-VPCConfig-assignPublicIp)": boolean,
               "[securityGroups](API_VPCConfig.md#robomaker-Type-VPCConfig-securityGroups)": [ "string" ],
               "[subnets](API_VPCConfig.md#robomaker-Type-VPCConfig-subnets)": [ "string" ]
            }
         }
      }
   ],
   "[failureCode](#robomaker-StartSimulationJobBatch-response-failureCode)": "string",
   "[failureReason](#robomaker-StartSimulationJobBatch-response-failureReason)": "string",
   "[pendingRequests](#robomaker-StartSimulationJobBatch-response-pendingRequests)": [ 
      { 
         "[dataSources](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-dataSources)": [ 
            { 
               "[name](API_DataSourceConfig.md#robomaker-Type-DataSourceConfig-name)": "string",
               "[s3Bucket](API_DataSourceConfig.md#robomaker-Type-DataSourceConfig-s3Bucket)": "string",
               "[s3Keys](API_DataSourceConfig.md#robomaker-Type-DataSourceConfig-s3Keys)": [ "string" ]
            }
         ],
         "[failureBehavior](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-failureBehavior)": "string",
         "[iamRole](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-iamRole)": "string",
         "[loggingConfig](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-loggingConfig)": { 
            "[recordAllRosTopics](API_LoggingConfig.md#robomaker-Type-LoggingConfig-recordAllRosTopics)": boolean
         },
         "[maxJobDurationInSeconds](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-maxJobDurationInSeconds)": number,
         "[outputLocation](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-outputLocation)": { 
            "[s3Bucket](API_OutputLocation.md#robomaker-Type-OutputLocation-s3Bucket)": "string",
            "[s3Prefix](API_OutputLocation.md#robomaker-Type-OutputLocation-s3Prefix)": "string"
         },
         "[robotApplications](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-robotApplications)": [ 
            { 
               "[application](API_RobotApplicationConfig.md#robomaker-Type-RobotApplicationConfig-application)": "string",
               "[applicationVersion](API_RobotApplicationConfig.md#robomaker-Type-RobotApplicationConfig-applicationVersion)": "string",
               "[launchConfig](API_RobotApplicationConfig.md#robomaker-Type-RobotApplicationConfig-launchConfig)": { 
                  "[environmentVariables](API_LaunchConfig.md#robomaker-Type-LaunchConfig-environmentVariables)": { 
                     "string" : "string" 
                  },
                  "[launchFile](API_LaunchConfig.md#robomaker-Type-LaunchConfig-launchFile)": "string",
                  "[packageName](API_LaunchConfig.md#robomaker-Type-LaunchConfig-packageName)": "string",
                  "[portForwardingConfig](API_LaunchConfig.md#robomaker-Type-LaunchConfig-portForwardingConfig)": { 
                     "[portMappings](API_PortForwardingConfig.md#robomaker-Type-PortForwardingConfig-portMappings)": [ 
                        { 
                           "[applicationPort](API_PortMapping.md#robomaker-Type-PortMapping-applicationPort)": number,
                           "[enableOnPublicIp](API_PortMapping.md#robomaker-Type-PortMapping-enableOnPublicIp)": boolean,
                           "[jobPort](API_PortMapping.md#robomaker-Type-PortMapping-jobPort)": number
                        }
                     ]
                  }
               }
            }
         ],
         "[simulationApplications](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-simulationApplications)": [ 
            { 
               "[application](API_SimulationApplicationConfig.md#robomaker-Type-SimulationApplicationConfig-application)": "string",
               "[applicationVersion](API_SimulationApplicationConfig.md#robomaker-Type-SimulationApplicationConfig-applicationVersion)": "string",
               "[launchConfig](API_SimulationApplicationConfig.md#robomaker-Type-SimulationApplicationConfig-launchConfig)": { 
                  "[environmentVariables](API_LaunchConfig.md#robomaker-Type-LaunchConfig-environmentVariables)": { 
                     "string" : "string" 
                  },
                  "[launchFile](API_LaunchConfig.md#robomaker-Type-LaunchConfig-launchFile)": "string",
                  "[packageName](API_LaunchConfig.md#robomaker-Type-LaunchConfig-packageName)": "string",
                  "[portForwardingConfig](API_LaunchConfig.md#robomaker-Type-LaunchConfig-portForwardingConfig)": { 
                     "[portMappings](API_PortForwardingConfig.md#robomaker-Type-PortForwardingConfig-portMappings)": [ 
                        { 
                           "[applicationPort](API_PortMapping.md#robomaker-Type-PortMapping-applicationPort)": number,
                           "[enableOnPublicIp](API_PortMapping.md#robomaker-Type-PortMapping-enableOnPublicIp)": boolean,
                           "[jobPort](API_PortMapping.md#robomaker-Type-PortMapping-jobPort)": number
                        }
                     ]
                  }
               }
            }
         ],
         "[tags](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-tags)": { 
            "string" : "string" 
         },
         "[useDefaultApplications](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-useDefaultApplications)": boolean,
         "[vpcConfig](API_SimulationJobRequest.md#robomaker-Type-SimulationJobRequest-vpcConfig)": { 
            "[assignPublicIp](API_VPCConfig.md#robomaker-Type-VPCConfig-assignPublicIp)": boolean,
            "[securityGroups](API_VPCConfig.md#robomaker-Type-VPCConfig-securityGroups)": [ "string" ],
            "[subnets](API_VPCConfig.md#robomaker-Type-VPCConfig-subnets)": [ "string" ]
         }
      }
   ],
   "[status](#robomaker-StartSimulationJobBatch-response-status)": "string",
   "[tags](#robomaker-StartSimulationJobBatch-response-tags)": { 
      "string" : "string" 
   }
}
```

## Response Elements<a name="API_StartSimulationJobBatch_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [arn](#API_StartSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-StartSimulationJobBatch-response-arn"></a>
The Amazon Resource Name \(arn\) of the batch\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*` 

 ** [batchPolicy](#API_StartSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-StartSimulationJobBatch-response-batchPolicy"></a>
The batch policy\.  
Type: [BatchPolicy](API_BatchPolicy.md) object

 ** [clientRequestToken](#API_StartSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-StartSimulationJobBatch-response-clientRequestToken"></a>
Unique, case\-sensitive identifier that you provide to ensure the idempotency of the request\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 64\.  
Pattern: `[a-zA-Z0-9_\-=]*` 

 ** [createdAt](#API_StartSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-StartSimulationJobBatch-response-createdAt"></a>
The time, in milliseconds since the epoch, when the simulation job batch was created\.  
Type: Timestamp

 ** [createdRequests](#API_StartSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-StartSimulationJobBatch-response-createdRequests"></a>
A list of created simulation job request summaries\.  
Type: Array of [SimulationJobSummary](API_SimulationJobSummary.md) objects  
Array Members: Minimum number of 0 items\. Maximum number of 100 items\.

 ** [failedRequests](#API_StartSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-StartSimulationJobBatch-response-failedRequests"></a>
A list of failed simulation job requests\. The request failed to be created into a simulation job\. Failed requests do not have a simulation job ID\.   
Type: Array of [FailedCreateSimulationJobRequest](API_FailedCreateSimulationJobRequest.md) objects

 ** [failureCode](#API_StartSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-StartSimulationJobBatch-response-failureCode"></a>
The failure code if the simulation job batch failed\.  
Type: String  
Valid Values:` InternalServiceError` 

 ** [failureReason](#API_StartSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-StartSimulationJobBatch-response-failureReason"></a>
The reason the simulation job batch failed\.  
Type: String

 ** [pendingRequests](#API_StartSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-StartSimulationJobBatch-response-pendingRequests"></a>
A list of pending simulation job requests\. These requests have not yet been created into simulation jobs\.  
Type: Array of [SimulationJobRequest](API_SimulationJobRequest.md) objects  
Array Members: Minimum number of 1 item\.

 ** [status](#API_StartSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-StartSimulationJobBatch-response-status"></a>
The status of the simulation job batch\.    
Pending  
The simulation job batch request is pending\.  
InProgress  
The simulation job batch is in progress\.   
Failed  
The simulation job batch failed\. One or more simulation job requests could not be completed due to an internal failure \(like `InternalServiceError`\)\. See `failureCode` and `failureReason` for more information\.  
Completed  
The simulation batch job completed\. A batch is complete when \(1\) there are no pending simulation job requests in the batch and none of the failed simulation job requests are due to `InternalServiceError` and \(2\) when all created simulation jobs have reached a terminal state \(for example, `Completed` or `Failed`\)\.   
Canceled  
The simulation batch job was cancelled\.  
Canceling  
The simulation batch job is being cancelled\.  
Completing  
The simulation batch job is completing\.  
TimingOut  
The simulation job batch is timing out\.  
If a batch timing out, and there are pending requests that were failing due to an internal failure \(like `InternalServiceError`\), the batch status will be `Failed`\. If there are no such failing request, the batch status will be `TimedOut`\.   
TimedOut  
The simulation batch job timed out\.
Type: String  
Valid Values:` Pending | InProgress | Failed | Completed | Canceled | Canceling | Completing | TimingOut | TimedOut` 

 ** [tags](#API_StartSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-StartSimulationJobBatch-response-tags"></a>
A map that contains tag keys and tag values that are attached to the deployment job batch\.  
Type: String to string map  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Key Pattern: `[a-zA-Z0-9 _.\-\/+=:]*`   
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.  
Value Pattern: `[a-zA-Z0-9 _.\-\/+=:]*` 

## Errors<a name="API_StartSimulationJobBatch_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **IdempotentParameterMismatchException**   
The request uses the same client token as a previous, but non\-identical request\. Do not reuse a client token with different requests, unless the requests are identical\.   
HTTP Status Code: 400

 **InternalServerException**   
AWS RoboMaker experienced a service issue\. Try your call again\.  
HTTP Status Code: 500

 **InvalidParameterException**   
A parameter specified in a request is not valid, is unsupported, or cannot be used\. The returned message provides an explanation of the error value\.  
HTTP Status Code: 400

 **LimitExceededException**   
The requested resource exceeds the maximum number allowed, or the number of concurrent stream requests exceeds the maximum number allowed\.   
HTTP Status Code: 400

 **ThrottlingException**   
AWS RoboMaker is temporarily unable to process the request\. Try your call again\.  
HTTP Status Code: 400

## See Also<a name="API_StartSimulationJobBatch_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/robomaker-2018-06-29/StartSimulationJobBatch) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/robomaker-2018-06-29/StartSimulationJobBatch) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/StartSimulationJobBatch) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/StartSimulationJobBatch) 
+  [AWS SDK for Java](https://docs.aws.amazon.com/goto/SdkForJava/robomaker-2018-06-29/StartSimulationJobBatch) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/robomaker-2018-06-29/StartSimulationJobBatch) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/robomaker-2018-06-29/StartSimulationJobBatch) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/robomaker-2018-06-29/StartSimulationJobBatch) 
+  [AWS SDK for Ruby V2](https://docs.aws.amazon.com/goto/SdkForRubyV2/robomaker-2018-06-29/StartSimulationJobBatch) 