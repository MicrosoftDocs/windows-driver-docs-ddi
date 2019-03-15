---
UID: NC:ntddk.PSHED_PI_SET_ERROR_SOURCE_INFO
title: PSHED_PI_SET_ERROR_SOURCE_INFO (ntddk.h)
description: A PSHED plug-in's SetErrorSourceInfo callback function configures an error source.
old-location: whea\seterrorsourceinfo.htm
tech.root: whea
ms.assetid: 0b9cd546-d4ad-4e0e-92cb-7994c7327977
ms.date: 02/20/2018
ms.keywords: PSHED_PI_SET_ERROR_SOURCE_INFO, PSHED_PI_SET_ERROR_SOURCE_INFO callback, SetErrorSourceInfo, SetErrorSourceInfo callback function [WHEA Drivers and Applications], ntddk/SetErrorSourceInfo, whea.seterrorsourceinfo, whearef_49924aa5-519d-4e23-95c5-a52264713258.xml
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ntddk.h
api_name:
- SetErrorSourceInfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# PSHED_PI_SET_ERROR_SOURCE_INFO callback function


## -description


A PSHED plug-in's <i>SetErrorSourceInfo</i> callback function configures an error source.


## -parameters




### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560617">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure when the PSHED plug-in called the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559466">PshedRegisterPlugin</a> function to register itself with the PSHED.


### -param ErrorSource [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560505">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure that describes the error source that is being configured.


## -returns



A PSHED plug-in's <i>SetErrorSourceInfo</i> callback function returns one of the following NTSTATUS codes:

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
The error source was successfully configured.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The PSHED plug-in does not support configuration of the specified error source.

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



A PSHED plug-in that participates in error source control sets the <b>Callbacks.SetErrorSourceInfo</b>, <b>Callbacks.EnableErrorSource</b>, and <b>Callbacks.DisableErrorSource</b> members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560617">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure to point to its <i>SetErrorSourceInfo</i>, <a href="https://msdn.microsoft.com/f2bc3b38-003e-4078-9bbd-d535e8971491">EnableErrorSource</a>, and <a href="https://msdn.microsoft.com/062927db-9581-447a-820b-82687710ea8d">DisableErrorSource</a> callback functions when the plug-in calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559466">PshedRegisterPlugin</a> function to register itself with the PSHED. The PSHED plug-in must also set the <b>PshedFAErrorSourceControl</b> flag in the <b>FunctionalAreaMask</b> member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

The Windows kernel calls into the PSHED to configure an error source in response to an error source configuration request by a WHEA management application. If a PSHED plug-in is registered to participate in error source control, the PSHED calls the PSHED plug-in's <i>SetErrorSourceInfo</i> callback function to give the PSHED plug-in an opportunity to perform the error source configuration operation. The error source configuration data is included in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560505">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure that is pointed to by the <i>ErrorSource</i> parameter.

If the PSHED plug-in does not support configuration of the specified error source, the <i>SetErrorSourceInfo</i> callback function returns STATUS_NOT_SUPPORTED. In this situation, the PSHED performs the requested error source configuration operation.

If the PSHED plug-in's supports configuration of the specified error source, the <i>SetErrorSourceInfo</i> callback function should save the error source's configuration data in the registry, in the system's BIOS tables, or in some other form of nonvolatile data storage that is available to the error source. The specific form of nonvolatile data storage that is used by an error source for storing the error source's configuration data is implementation-specific. The <i>SetErrorSourceInfo</i> callback function should apply the configuration data to the error source in such a way that the configuration changes become effective the next time that the system is restarted. When the system is restarted, the PSHED plug-in should report the new error source configuration data for the error source to the operating system during error source discovery.




## -see-also




<a href="https://msdn.microsoft.com/062927db-9581-447a-820b-82687710ea8d">DisableErrorSource</a>



<a href="https://msdn.microsoft.com/f2bc3b38-003e-4078-9bbd-d535e8971491">EnableErrorSource</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559466">PshedRegisterPlugin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560505">WHEA_ERROR_SOURCE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560617">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a>
 

 

