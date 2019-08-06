---
UID: NF:fwpsk.FwpsDereferencevSwitchPacketContext0
title: FwpsDereferencevSwitchPacketContext0 function (fwpsk.h)
description: This function is not supported.
old-location: netvista\fwpsdereferencevswitchpacketcontext0.htm
tech.root: netvista
ms.assetid: 9A315227-7305-4068-81DE-BD25F733E650
ms.date: 05/02/2018
ms.keywords: FwpsDereferencevSwitchPacketContext0, FwpsDereferencevSwitchPacketContext0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsDereferencevSwitchPacketContext0, netvista.fwpsdereferencevswitchpacketcontext0
ms.topic: function
f1_keywords:
 - "fwpsk/FwpsDereferencevSwitchPacketContext0"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- fwpkclnt.lib
- fwpkclnt.dll
api_name:
- FwpsDereferencevSwitchPacketContext0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpsDereferencevSwitchPacketContext0 function


## -description


This function is not supported.


## -parameters




### -param packetContext

The <b>vSwitchPacketContext</b> value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">FWPS_INCOMING_METADATA_VALUES0</a> structure that is passed to callouts during virtual switch transport layer classifies (the FWPS_L2_METADATA_FIELD_VSWITCH_SOURCE_PORT_ID bit will be set in the <b>currentL2MetadataValues</b> member). 


## -returns



None.




## -remarks



The <b>FwpsDereferencevSwitchPacketContext0</b> function releases a reference  that was acquired by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsreferencevswitchpacketcontext0">FwpsReferencevSwitchPacketContext0</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">FWPS_INCOMING_METADATA_VALUES0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsreferencevswitchpacketcontext0">FwpsReferencevSwitchPacketContext0</a>
 

 

