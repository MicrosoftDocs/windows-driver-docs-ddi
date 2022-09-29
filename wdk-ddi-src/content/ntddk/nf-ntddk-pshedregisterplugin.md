---
UID: NF:ntddk.PshedRegisterPlugin
title: PshedRegisterPlugin function (ntddk.h)
description: The PshedRegisterPlugin function registers a PSHED plug-in with the PSHED.
old-location: whea\pshedregisterplugin.htm
tech.root: whea
ms.date: 02/20/2018
keywords: ["PshedRegisterPlugin function"]
ms.keywords: PshedRegisterPlugin, PshedRegisterPlugin function [WHEA Drivers and Applications], ntddk/PshedRegisterPlugin, whea.pshedregisterplugin, whearef_27f04399-dd53-44b3-a31e-350aee53bcb1.xml
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PshedRegisterPlugin
 - ntddk/PshedRegisterPlugin
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Pshed.dll
api_name:
 - PshedRegisterPlugin
---

# PshedRegisterPlugin function


## -description

The <b>PshedRegisterPlugin</b> function registers a PSHED plug-in with the PSHED.

## -parameters

### -param Packet [in, out]


A pointer to an initialized  <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure that describes the PSHED plug-in's registration information.

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

A PSHED plug-in calls the <b>PshedRegisterPlugin</b> function to register itself with the PSHED. A PSHED plug-in typically calls this function from within either its <a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> function or its <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> function.

Starting in Windows 10, version 1903 (WDK 10 version 18362), a V2 of the PSHED-Plugin interfaces is available that allows a plugin to be removed and updated on a running system by calling the PshedUnregisterPlugin function. Because they can be unregistered, V2 plugins cannot specify the PshedFADiscovery flag (discovery functional area) in the FunctionalAreaMask member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V2 structure. For info about registering a plug-in, see Registering a PSHED Plug-In. For a V1 plugin, if you try to unregister, a bugcheck may occur. It is recommended that you use a V2 plugin if possible, which is the current default.

To register a V1 vs a V2 plugin, use the correct struct. [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V1**](./ns-ntddk-whea_pshed_plugin_registration_packet_v1.md) for V1 and [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V2**](./ns-ntddk-whea_pshed_plugin_registration_packet_v2.md) for V2. 

A V2 plugin can still add error sources as described in [Using WHEA on Windows 10](/windows-hardware/drivers/whea/using-whea-on-windows-10), or by calling [**WheaAddErrorSource**](./nf-ntddk-wheaadderrorsource.md) and [**WheaRemoveErrorSource**](./nf-ntddk-whearemoveerrorsource.md).

A plugin may continue to use the discovery functional area by specifying **WHEA_PLUGIN_REGISTRATION_PACKET_V1** as the version of its [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V2**](./ns-ntddk-whea_pshed_plugin_registration_packet_v2.md) structure.

All callbacks, on both V1 and V2 plugins, are called at a minimum IRQL of DISPATCH_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a>



<a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a>
