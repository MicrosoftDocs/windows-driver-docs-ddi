---
UID: NC:ntddk.PSHED_PI_GET_ERROR_SOURCE_INFO
title: PSHED_PI_GET_ERROR_SOURCE_INFO (ntddk.h)
description: A PSHED plug-in's GetErrorSourceInfo callback function returns an error source descriptor structure that represents a particular error source that is implemented by the hardware platform.
old-location: whea\geterrorsourceinfo.htm
tech.root: whea
ms.assetid: 8ede391a-acda-4540-a8bb-1b232695d632
ms.date: 02/20/2018
ms.keywords: GetErrorSourceInfo, GetErrorSourceInfo callback function [WHEA Drivers and Applications], PSHED_PI_GET_ERROR_SOURCE_INFO, PSHED_PI_GET_ERROR_SOURCE_INFO callback, ntddk/GetErrorSourceInfo, whea.geterrorsourceinfo, whearef_977e9d78-23ec-408f-ba18-a4a96f9a8e62.xml
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
- GetErrorSourceInfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# PSHED_PI_GET_ERROR_SOURCE_INFO callback function


## -description


A PSHED plug-in's <i>GetErrorSourceInfo</i> callback function returns an error source descriptor structure that represents a particular error source that is implemented by the hardware platform.


## -parameters




### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560617">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure when the PSHED plug-in called the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559466">PshedRegisterPlugin</a> function to register itself with the PSHED.


### -param ErrorSource [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560505">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure that represents a particular error source that is implemented by the hardware platform.


## -returns



A PSHED plug-in's <i>GetErrorSourceInfo</i> callback function returns one of the following NTSTATUS codes:

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
The error source information was successfully updated.

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



A PSHED plug-in that participates in error source discovery sets the <b>Callbacks.GetAllErrorSources </b>member and, optionally, the <b>Callbacks.GetErrorSourceInfo </b>member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560617">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure to point to its <a href="https://msdn.microsoft.com/e9c97f88-aa13-4a3e-9236-c09703d17e4b">GetAllErrorSources</a> and <i>GetErrorSourceInfo</i> callback functions when the plug-in calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559466">PshedRegisterPlugin</a> function to register itself with the PSHED. The PSHED plug-in must also set the <b>PshedFADiscovery</b> flag in the <b>FunctionalAreaMask</b> member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

The Windows kernel calls into the PSHED to obtain additional details about a particular error source. This occurs when a new error source is added to the system by a bus driver. For example, when the PCI driver discovers a PCI Express (PCIe) device that is capable of reporting PCIe errors, it reports the error source to the operating system.

If a PSHED plug-in is registered to participate in error source discovery and it has implemented a <i>GetErrorSourceInfo</i> callback function, after the PSHED has updated the error source descriptor structure with the information that it has collected about the error source, the PSHED calls the PSHED plug-in's <i>GetErrorSourceInfo</i> callback function so that the PSHED plug-in can provide additional details about the error source. The <i>GetErrorSourceInfo</i> callback function updates the contents of the error source descriptor structure so that it accurately represents the error source as it is implemented by the hardware platform.




## -see-also




<a href="https://msdn.microsoft.com/e9c97f88-aa13-4a3e-9236-c09703d17e4b">GetAllErrorSources</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559466">PshedRegisterPlugin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560505">WHEA_ERROR_SOURCE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560617">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a>
 

 

