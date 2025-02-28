---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ClusterAwareUpdating.dll-Help.xml
Module Name: ClusterAwareUpdating
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/clusterawareupdating/save-caudebugtrace?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Save-CauDebugTrace
---

# Save-CauDebugTrace

## SYNOPSIS
Saves CAU debug tracing information to a local zip file.

## SYNTAX

```
Save-CauDebugTrace [[-ClusterName] <String>] [[-FilePath] <String>] [-Credential <PSCredential>]
 [-RunId <Guid>] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Save-CauDebugTrace** cmdlet saves Cluster-Aware Updating (CAU) debug tracing information to a local zip file.
The tracing information is mainly intended for use by developers and support engineers.
Specify the file name with the *FilePath* parameter.

To run this cmdlet, Windows PowerShell remoting must be enabled on each node.
To do this, run the **Enable-PSRemoting** cmdlet.
In addition, ensure that the **Windows Remote Management - Compatibility Mode (HTTP-In)** firewall exception is enabled on each node.

## EXAMPLES

### Example 1: Save debug tracing information for the specified cluster
```
PS C:\> Save-CauDebugTrace -ClusterName "CONTOSO-FC1" -FilePath "C:\temp\testrun.zip"
```

This command saves the debug tracing information for the cluster named CONTOSO-FC1, to a trace file called testrun.zip in the C:\temp folder.

## PARAMETERS

### -ClusterName
Specifies the name of the cluster for which to gather CAU debug tracing information.
This parameter is only required when this cmdlet is not run on a failover cluster node, or this cmdlet is used to reference a failover cluster different from where the cmdlet is run.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the administrative credentials for the target cluster.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath
Specifies the name of the file to which to save the tracing information, such as `MyTrace.zip`.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Path

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: f

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunId
Indicates that the cmdlet should only include debug trace files related to an updating run with the specified Run ID.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Invoke-CauRun](./Invoke-CauRun.md)

