---
UID: NC:ntddk.PSHED_PI_INJECT_ERROR
title: PSHED_PI_INJECT_ERROR
author: windows-driver-content
description: A PSHED plug-in's InjectError callback function injects an error into the hardware platform.
old-location: whea\injecterror.htm
old-project: whea
ms.assetid: efd2658b-875e-4589-9ba0-42232e070b91
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: whea.injecterror, InjectError callback function [WHEA Drivers and Applications], InjectError, PSHED_PI_INJECT_ERROR, PSHED_PI_INJECT_ERROR, ntddk/InjectError, whearef_377f07ab-4ea0-4982-8298-c7139b4bfdc7.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ntddk.h
apiname:
-	InjectError
product: Windows
targetos: Windows
req.typenames: "*PFILTER_INITIALIZATION_DATA, FILTER_INITIALIZATION_DATA"
---

# PSHED_PI_INJECT_ERROR callback


## -description


A PSHED plug-in's <i>InjectError </i>callback function injects an error into the hardware platform.


## -prototype


````
PSHED_PI_INJECT_ERROR InjectError;

NTSTATUS InjectError(
  _Inout_opt_ PVOID     PluginContext,
  _In_        ULONGLONG ErrorType,
  _In_        ULONGLONG Parameter1,
  _In_        ULONGLONG Parameter2,
  _In_        ULONGLONG Parameter3,
  _In_        ULONGLONG Parameter4
)
{ ... }
````


## -parameters




### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the <b>Context</b> member of the <a href="..\ntddk\ns-ntddk-_whea_pshed_plugin_registration_packet.md">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure when the PSHED plug-in called the <a href="..\ntddk\nf-ntddk-pshedregisterplugin.md">PshedRegisterPlugin</a> function to register itself with the PSHED.


### -param ErrorType [in]

The type of error to be injected into the hardware platform. Possible values are:




#### INJECT_ERRTYPE_MEMORY_CORRECTABLE

A correctable memory error.


#### INJECT_ERRTYPE_MEMORY_UNCORRECTABLEFATAL

An uncorrectable fatal memory error.


#### INJECT_ERRTYPE_MEMORY_UNCORRECTABLENONFATAL

An uncorrectable nonfatal memory error.


#### INJECT_ERRTYPE_PCIEXPRESS_CORRECTABLE

A correctable PCI Express error.


#### INJECT_ERRTYPE_PCIEXPRESS_UNCORRECTABLEFATAL

An uncorrectable fatal PCI Express error.


#### INJECT_ERRTYPE_PCIEXPRESS_UNCORRECTABLENONFATAL

An uncorrectable nonfatal PCI Express error.


#### INJECT_ERRTYPE_PLATFORM_CORRECTABLE

A correctable platform error.


#### INJECT_ERRTYPE_PLATFORM_UNCORRECTABLEFATAL

An uncorrectable fatal platform error.


#### INJECT_ERRTYPE_PLATFORM_UNCORRECTABLENONFATAL

An uncorrectable nonfatal platform error.


#### INJECT_ERRTYPE_PROCESSOR_CORRECTABLE

A correctable processor error.


#### INJECT_ERRTYPE_PROCESSOR_UNCORRECTABLEFATAL

An uncorrectable fatal processor error.


#### INJECT_ERRTYPE_PROCESSOR_UNCORRECTABLENONFATAL

An uncorrectable nonfatal processor error.


### -param Parameter1 [in]

A generic parameter that contains additional data that is passed by the WHEA management application that is injecting the error.


### -param Parameter2 [in]

A generic parameter that contains additional data that is passed by the WHEA management application that is injecting the error.


### -param Parameter3 [in]

A generic parameter that contains additional data that is passed by the WHEA management application that is injecting the error.


### -param Parameter4 [in]

A generic parameter that contains additional data that is passed by the WHEA management application that is injecting the error.


## -returns


A PSHED plug-in's <i>InjectError</i> callback function returns one of the following NTSTATUS codes:
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
The error was successfully injected into the hardware platform.

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

<div class="alert"><b>Note</b>  For injected errors that are fatal or otherwise unrecoverable, this callback function might not return before the operating system generates a bug check in response to the error condition.</div>
<div> </div>
</td>
</tr>
</table> 



## -remarks


A PSHED plug-in that participates in error injection sets the <b>Callbacks.GetInjectionCapabilities </b>and <b>Callbacks.InjectError </b>members of the <a href="..\ntddk\ns-ntddk-_whea_pshed_plugin_registration_packet.md">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure to point to its <a href="..\ntddk\nc-ntddk-pshed_pi_get_injection_capabilities.md">GetInjectionCapabilities</a> and <i>InjectError</i> callback functions when the plug-in calls the <a href="..\ntddk\nf-ntddk-pshedregisterplugin.md">PshedRegisterPlugin</a> function to register itself with the PSHED. The PSHED plug-in must also set the <b>PshedFAErrorInjection</b> flag in the <b>FunctionalAreaMask</b> member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

When a WHEA management application makes a request to inject a hardware error, the Windows kernel calls into the PSHED to inject the error into the hardware platform. If a PSHED plug-in is registered to participate in error injection, the PSHED calls the PSHED plug-in's <i>InjectError </i>callback function to perform the error injection operation.

The WHEA management application that is injecting the error can pass additional error-specific data to the PSHED plug-in's <i>InjectError </i>callback function by using parameters <i>Parameter1</i> through <i>Parameter4</i>. For example, on Itanium-based systems, some of the error injection operations require an accompanying address. In this situation, the WHEA management application can pass the address to the PSHED plug-in's <i>InjectError </i>callback function using one of these parameters.



## -see-also

<a href="..\ntddk\ns-ntddk-_whea_pshed_plugin_registration_packet.md">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a>

<a href="..\ntddk\nc-ntddk-pshed_pi_get_injection_capabilities.md">GetInjectionCapabilities</a>

<a href="..\ntddk\nf-ntddk-pshedregisterplugin.md">PshedRegisterPlugin</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20PSHED_PI_INJECT_ERROR callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

