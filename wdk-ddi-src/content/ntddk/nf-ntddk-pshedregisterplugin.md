---
UID: NF:ntddk.PshedRegisterPlugin
title: PshedRegisterPlugin function
author: windows-driver-content
description: The PshedRegisterPlugin function registers a PSHED plug-in with the PSHED.
old-location: whea\pshedregisterplugin.htm
old-project: whea
ms.assetid: 8ad93312-932c-417c-8198-9ba515e3d55d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: whearef_27f04399-dd53-44b3-a31e-350aee53bcb1.xml, PshedRegisterPlugin, ntddk/PshedRegisterPlugin, PshedRegisterPlugin function [WHEA Drivers and Applications], whea.pshedregisterplugin
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
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
req.lib: Pshed.lib
req.dll: Pshed.dll
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Pshed.dll
apiname:
-	PshedRegisterPlugin
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PshedRegisterPlugin function


## -description


The <b>PshedRegisterPlugin</b> function registers a PSHED plug-in with the PSHED.


## -syntax


````
NTSTATUS PshedRegisterPlugin(
  _Inout_ PWHEA_PSHED_PLUGIN_REGISTRATION_PACKET Packet
);
````


## -parameters




### -param Packet [in, out]

A pointer to an initialized  <a href="..\ntddk\ns-ntddk-_whea_pshed_plugin_registration_packet.md">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure that describes the PSHED plug-in's registration information.


## -returns


<b>PshedRegisterPlugin</b> returns one of the following NTSTATUS codes:
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
The PSHED plug-in was successfully registered.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The data in the supplied registration packet is invalid.

</td>
</tr>
</table> 



## -remarks


A PSHED plug-in calls the <b>PshedRegisterPlugin</b> function to register itself with the PSHED. A PSHED plug-in typically calls this function from within either its <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> function or its <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> function.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a>

<a href="..\ntddk\ns-ntddk-_whea_pshed_plugin_registration_packet.md">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a>

<a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20PshedRegisterPlugin function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

