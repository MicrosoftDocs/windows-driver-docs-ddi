---
UID: NC:ntddk.PSHED_PI_CLEAR_ERROR_STATUS
title: PSHED_PI_CLEAR_ERROR_STATUS
author: windows-driver-content
description: A PSHED plug-in's ClearErrorStatus callback function clears any platform-specific error status registers for a corrected hardware error condition.
old-location: whea\clearerrorstatus.htm
tech.root: whea
ms.assetid: 8b29edf3-be7f-4a8d-af96-2b1e985ba061
ms.date: 02/20/2018
ms.keywords: ClearErrorStatus, ClearErrorStatus callback function [WHEA Drivers and Applications], PSHED_PI_CLEAR_ERROR_STATUS, PSHED_PI_CLEAR_ERROR_STATUS callback, ntddk/ClearErrorStatus, whea.clearerrorstatus, whearef_022b6321-f051-4d35-ad0c-e6528d03a411.xml
ms.topic: callback
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= HIGH_LEVEL (See Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ntddk.h
api_name:
-	ClearErrorStatus
product:
- Windows
targetos: Windows
req.typenames: 
---

# PSHED_PI_CLEAR_ERROR_STATUS callback function


## -description


A PSHED plug-in's <i>ClearErrorStatus</i> callback function clears any platform-specific error status registers for a corrected hardware error condition.


## -parameters




### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560617">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure when the PSHED plug-in called the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559466">PshedRegisterPlugin</a> function to register itself with the PSHED.


### -param ErrorSource [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560505">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure that describes the error source that reported the hardware error.


### -param BufferLength [in]

The size, in bytes, of the buffer pointed to by the <i>ErrorRecord</i> parameter.


### -param ErrorRecord [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560483">WHEA_ERROR_RECORD</a> structure that describes an error record. The error record describes the corrected hardware error condition for which the platform-specific error status registers are being cleared.


## -returns



A PSHED plug-in's <i>ClearErrorStatus</i> callback function returns one of the following NTSTATUS codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The platform-specific error status registers for the corrected hardware error condition were successfully cleared.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The PSHED plug-in does not support the specified error source.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>
 




## -remarks



A PSHED plug-in that participates in error information retrieval sets the <b>Callbacks.RetrieveErrorInfo</b>, <b>Callbacks.FinalizeErrorRecord</b>, and <b>Callbacks.ClearErrorStatus</b> members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560617">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure to point to its <a href="https://msdn.microsoft.com/4d299057-a1cc-4b53-8ab4-031672181e74">RetrieveErrorInfo</a>, <a href="https://msdn.microsoft.com/68461243-ddf4-4883-84d2-4c105f1634b2">FinalizeErrorRecord</a>, and <i>ClearErrorStatus</i> callback functions when the plug-in calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559466">PshedRegisterPlugin</a> function to register itself with the PSHED. The PSHED plug-in must also set the <b>PshedFAErrorInfoRetrieval</b> flag in the <b>FunctionalAreaMask</b> member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

For corrected hardware error conditions, the Windows kernel calls into the PSHED to clear the error source's error status registers as the final step of processing the error. If a PSHED plug-in is registered to participate in error information retrieval, the PSHED calls the PSHED plug-in's <i>ClearErrorStatus</i> callback function so that the PSHED plug-in can clear any additional platform-specific error status registers.

The PSHED calls a PSHED plug-in's <i>ClearErrorStatus</i> callback function at IRQL &lt;= HIGH_LEVEL. The exact IRQL at which this callback function is called depends on the specific type of hardware error that occurred.




## -see-also




<a href="https://msdn.microsoft.com/68461243-ddf4-4883-84d2-4c105f1634b2">FinalizeErrorRecord</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559466">PshedRegisterPlugin</a>



<a href="https://msdn.microsoft.com/4d299057-a1cc-4b53-8ab4-031672181e74">RetrieveErrorInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560483">WHEA_ERROR_RECORD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560505">WHEA_ERROR_SOURCE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560617">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a>
 

 

