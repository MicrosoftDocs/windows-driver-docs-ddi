---
UID: NF:fwpsk.FwpsDereferencevSwitchPacketContext0
title: FwpsDereferencevSwitchPacketContext0 function
author: windows-driver-content
description: This function is not supported.
old-location: netvista\fwpsdereferencevswitchpacketcontext0.htm
old-project: netvista
ms.assetid: 9A315227-7305-4068-81DE-BD25F733E650
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FwpsDereferencevSwitchPacketContext0, FwpsDereferencevSwitchPacketContext0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsDereferencevSwitchPacketContext0, netvista.fwpsdereferencevswitchpacketcontext0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	fwpkclnt.lib
-	fwpkclnt.dll
api_name:
-	FwpsDereferencevSwitchPacketContext0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsDereferencevSwitchPacketContext0 function


## -description


This function is not supported.


## -syntax


````
void NTAPI FwpsDereferencevSwitchPacketContext0(
   _Inout_ HANDLE packetContext
);
````


## -parameters




### -param packetContext

The <b>vSwitchPacketContext</b> value in the <a href="..\fwpsk\ns-fwpsk-fwps_incoming_metadata_values0_.md">FWPS_INCOMING_METADATA_VALUES0</a> structure that is passed to callouts during virtual switch transport layer classifies (the FWPS_L2_METADATA_FIELD_VSWITCH_SOURCE_PORT_ID bit will be set in the <b>currentL2MetadataValues</b> member). 


## -returns



None.




## -remarks



The <b>FwpsDereferencevSwitchPacketContext0</b> function releases a reference  that was acquired by the <a href="..\fwpsk\nf-fwpsk-fwpsreferencevswitchpacketcontext0.md">FwpsReferencevSwitchPacketContext0</a> function.




## -see-also

<a href="..\fwpsk\ns-fwpsk-fwps_incoming_metadata_values0_.md">FWPS_INCOMING_METADATA_VALUES0</a>



<a href="..\fwpsk\nf-fwpsk-fwpsreferencevswitchpacketcontext0.md">FwpsReferencevSwitchPacketContext0</a>



 

 


