### Example 1: Creates or updates compute. This call will overwrite a compute if it exists
```powershell
# The datastore type includes 'AKS', 'Kubernetes', 'AmlCompute', 'ComputeInstance','DataFactory', 'VirtualMachine', 'HDInsight', 'Databricks', 'DataLakeAnalytics', 'SynapseSpark'.
# You can use following command to create it then pass it as value to Compute parameter of the New-AzMlWorkspaceCompute cmdlet.
# New-AzMLWorkspaceAmlComputeObject
# New-AzMLWorkspaceComputeInstanceObject
# New-AzMLWorkspaceAksObject
# New-AzMLWorkspaceKubernetesObject
# New-AzMLWorkspaceVirtualMachineObject
# New-AzMLWorkspaceHDInsightObject
# New-AzMLWorkspaceDataFactoryObject
# New-AzMLWorkspaceDatabricksObject
# New-AzMLWorkspaceDataLakeAnalyticsObject
# New-AzMLWorkspaceSynapseSparkObject

$aml = New-AzMLWorkspaceAmlComputeObject -OSType 'Linux' -VMSize "STANDARD_DS3_V2" `
-ScaleSettingMaxNodeCount 8 -ScaleSettingMinNodeCount 0 -RemoteLoginPortPublicAccess 'NotSpecified' -EnableNodePublicIP $true
New-AzMlWorkspaceCompute -ResourceGroupName ml-rg-test -WorkspaceName mlworkspace-test01 -Name aml02 -Location eastus -Compute $aml
```

```output
Name        SystemDataCreatedAt SystemDataCreatedBy SystemDataCreatedByType SystemDataLastModifiedAt SystemDataLastModifiedBy SystemDataLastModifiedByType AzureAsyncOperation Location ResourceGroupName
----        ------------------- ------------------- ----------------------- ------------------------ ------------------------ ---------------------------- ------------------- -------- -----------------
aml02   
```

Creates or updates compute. This call will overwrite a compute if it exists