---
UID: NC:ntddk.PSHED_PI_GET_ALL_ERROR_SOURCES
title: PSHED_PI_GET_ALL_ERROR_SOURCES
author: windows-driver-content
description: A PSHED plug-in's GetAllErrorSources callback function returns a list of error source descriptor structures that represents all of the error sources that are implemented by the hardware platform.
old-location: whea\getallerrorsources.htm
old-project: whea
ms.assetid: e9c97f88-aa13-4a3e-9236-c09703d17e4b
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: GetAllErrorSources, GetAllErrorSources callback function [WHEA Drivers and Applications], PSHED_PI_GET_ALL_ERROR_SOURCES, ntddk/GetAllErrorSources, whea.getallerrorsources, whearef_fe2e1679-84ee-4f90-8615-24cbab3cb686.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ntddk.h
api_name:
-	GetAllErrorSources
product: Windows
targetos: Windows
req.typenames: FILTER_INITIALIZATION_DATA, *PFILTER_INITIALIZATION_DATA
---

# PSHED_PI_GET_ALL_ERROR_SOURCES callback


## -description


A PSHED plug-in's <i>GetAllErrorSources</i> callback function returns a list of error source descriptor structures that represents all of the error sources that are implemented by the hardware platform.


## -parameters




### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560617">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure when the PSHED plug-in called the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559466">PshedRegisterPlugin</a> function to register itself with the PSHED.


### -param Count [in, out]

A pointer to a ULONG-typed variable. When the <i>GetAllErrorSources</i> callback function is called, this variable contains the number of error source descriptor structures that are contained in the buffer pointed to by the <i>ErrorSources</i> parameter as provided by the PSHED. If the <i>GetAllErrorSources</i> callback function changes the number of error source descriptor structures that are in the buffer, it must set this variable to the new number of error source descriptor structures before it returns.


### -param *ErrorSrcs


### -param Length [in, out]

A pointer to a ULONG-typed variable that contains the size, in bytes, of the buffer pointed to by the <i>ErrorSources</i> parameter. If the size is too small to contain the modified list of error source descriptor structures, the <i>GetAllErrorSources</i> callback function sets this variable to the buffer size that is required to contain the list and returns STATUS_BUFFER_TOO_SMALL.


#### - ErrorSources [in, out]

A pointer to a buffer that receives an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff560505">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structures that represents all of the error sources that are implemented by the hardware platform. When the <i>GetAllErrorSources</i> callback function is called, this buffer contains an initial list of error source descriptor structures that is provided by the PSHED. The PSHED plug-in can make changes to the list so that it accurately represents all of the error sources that are implemented by the hardware platform.


## -returns



A PSHED plug-in's <i>GetAllErrorSources</i> callback function returns one of the following NTSTATUS codes:

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
The modified list of error source descriptor structures was successfully returned in the buffer pointed to by the <i>ErrorSources</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The size of the buffer pointed to by the <i>ErrorSources</i> parameter is too small to contain the list of error source descriptor structures.

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



A PSHED plug-in that participates in error source discovery sets the <b>Callbacks.GetAllErrorSources </b>member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560617">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure to point to its <i>GetAllErrorSources</i> callback function when the plug-in calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559466">PshedRegisterPlugin</a> function to register itself with the PSHED. The PSHED plug-in must also set the <b>PshedFADiscovery</b> flag in the <b>FunctionalAreaMask</b> member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

When the operating system starts, the Windows kernel calls into the PSHED to retrieve the list of error source descriptor structures that represents all of the error sources that are implemented by the hardware platform. The PSHED creates an initial list of error source descriptor structures. If a PSHED plug-in is registered to participate in error source discovery, the PSHED calls the PSHED plug-in's <i>GetAllErrorSources</i> callback function. The PSHED plug-in can make any combination of the following changes to the list of error source descriptor structures so that it accurately represents all of the error sources that are implemented by the hardware platform.

<ul>
<li>
Modify the contents of one or more of the error source descriptor structures.

</li>
<li>
Remove one or more of the error source descriptor structures from the list.

</li>
<li>
Add one or more new error source descriptor structures to the list.

</li>
</ul>
If the PSHED plug-in must add one or more new error source descriptor structures to the list and the size of the buffer is too small to include the additional structures, the PSHED plug-in's <i>GetAllErrorSources</i> callback function must set the variable pointed to by the <i>Length </i>parameter to the buffer size that is required to contain the list with the additional structures and return STATUS_BUFFER_TOO_SMALL. In this situation, the PSHED will allocate a larger buffer, copy the list of error source descriptor structures into the new buffer, and call the PSHED plug-in's <i>GetAllErrorSources</i> callback function a second time.

A PSHED plug-in that participates in error source discovery can also implement an optional <a href="https://msdn.microsoft.com/8ede391a-acda-4540-a8bb-1b232695d632">GetErrorSourceInfo</a> callback function. In this situation, the PSHED plug-in also sets the <b>Callbacks.GetErrorSourceInfo </b>member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560617">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure to point to its <i>GetErrorSourceInfo</i> callback function when it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559466">PshedRegisterPlugin</a> function to register itself with the PSHED.




## -see-also




<a href="https://msdn.microsoft.com/8ede391a-acda-4540-a8bb-1b232695d632">GetErrorSourceInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559466">PshedRegisterPlugin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560505">WHEA_ERROR_SOURCE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560617">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a>
 

 

