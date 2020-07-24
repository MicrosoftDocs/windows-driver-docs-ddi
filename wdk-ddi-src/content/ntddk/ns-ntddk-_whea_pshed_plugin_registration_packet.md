---
UID: NS:ntddk._WHEA_PSHED_PLUGIN_REGISTRATION_PACKET
title: _WHEA_PSHED_PLUGIN_REGISTRATION_PACKET (ntddk.h)
description: The WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure describes the data required for registering a PSHED plug-in with the PSHED.
old-location: whea\whea_pshed_plugin_registration_packet.htm
tech.root: whea
ms.assetid: 9dafa65f-26f6-42a6-a125-013c61a66ccc
ms.date: 02/20/2018
keywords: ["_WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure"]
ms.keywords: "*PWHEA_PSHED_PLUGIN_REGISTRATION_PACKET, PWHEA_PSHED_PLUGIN_REGISTRATION_PACKET, PWHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure pointer [WHEA Drivers and Applications], WHEA_PSHED_PLUGIN_REGISTRATION_PACKET, WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure [WHEA Drivers and Applications], _WHEA_PSHED_PLUGIN_REGISTRATION_PACKET, ntddk/PWHEA_PSHED_PLUGIN_REGISTRATION_PACKET, ntddk/WHEA_PSHED_PLUGIN_REGISTRATION_PACKET, whea.whea_pshed_plugin_registration_packet, whearef_9e79e188-a1ce-4d98-a15d-a45c27f9e836.xml"
f1_keywords:
 - "ntddk/WHEA_PSHED_PLUGIN_REGISTRATION_PACKET"
 - "WHEA_PSHED_PLUGIN_REGISTRATION_PACKET"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- WHEA_PSHED_PLUGIN_REGISTRATION_PACKET
targetos: Windows
req.typenames: WHEA_PSHED_PLUGIN_REGISTRATION_PACKET, *PWHEA_PSHED_PLUGIN_REGISTRATION_PACKET
---

# _WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure


## -description


The WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure describes the data required for registering a PSHED plug-in with the PSHED.


## -struct-fields




### -field Length

The size, in bytes, of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.


### -field Version

The version of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure. PSHED plug-ins must set this member to WHEA_PLUGIN_REGISTRATION_PACKET_VERSION.


### -field Context

A PSHED plug-in-supplied context area that is passed to the PSHED plug-in's callback functions.


### -field FunctionalAreaMask

A bit-wise OR'ed combination of flags that specifies the functional areas in which the PSHED plug-in participates. Possible flags are:





#### PshedFADiscovery

The PSHED plug-in participates in error source discovery.



#### PshedFAErrorSourceControl

The PSHED plug-in participates in error source control.



#### PshedFAErrorRecordPersistence

The PSHED plug-in participates in error record persistence.



#### PshedFAErrorInfoRetrieval

The PSHED plug-in participates in error information retrieval.



#### PshedFAErrorRecovery

The PSHED plug-in participates in error recovery.



#### PshedFAErrorInjection

The PSHED plug-in participates in error injection.


### -field Reserved

Reserved for system use. PSHED plug-ins should set this member to zero.


### -field Callbacks

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_callbacks">WHEA_PSHED_PLUGIN_CALLBACKS</a> structure that describes the callback functions for the PSHED plug-in.


## -remarks



A PSHED plug-in passes an initialized WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin">PshedRegisterPlugin</a> function when it registers itself with the PSHED.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin">PshedRegisterPlugin</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_callbacks">WHEA_PSHED_PLUGIN_CALLBACKS</a>
 

 

