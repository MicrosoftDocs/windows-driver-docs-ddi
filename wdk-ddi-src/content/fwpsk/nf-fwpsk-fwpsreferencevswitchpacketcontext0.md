---
UID: NF:fwpsk.FwpsReferencevSwitchPacketContext0
title: FwpsReferencevSwitchPacketContext0 function
author: windows-driver-content
description: This function is not supported.
old-location: netvista\fwpsreferencevswitchpacketcontext0.htm
old-project: netvista
ms.assetid: F4F5005F-2BDA-4E58-A06A-2A4F1D34776D
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: FwpsReferencevSwitchPacketContext0, FwpsReferencevSwitchPacketContext0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsReferencevSwitchPacketContext0, netvista.fwpsreferencevswitchpacketcontext0
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
-	FwpsReferencevSwitchPacketContext0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsReferencevSwitchPacketContext0 function


## -description


This function is not supported.


## -syntax


````
void NTAPI FwpsReferencevSwitchPacketContext0(
   _Inout_ HANDLE packetContext
);
````


## -parameters




### -param packetContext

The <b>vSwitchPacketContext</b> value in the <a href="..\fwpsk\ns-fwpsk-fwps_incoming_metadata_values0_.md">FWPS_INCOMING_METADATA_VALUES0</a> structure that is passed to callouts during virtual switch transport layer classifies (the <b>FWPS_L2_METADATA_FIELD_VSWITCH_SOURCE_PORT_ID</b> bit will be set in the  <b>currentL2MetadataValues</b> member). 


## -returns



None.




## -remarks




    The  <b>FwpsReferencevSwitchPacketContext0</b> function processes the <b>vSwitchPacketContext</b> member  in  the <a href="..\fwpsk\ns-fwpsk-fwps_incoming_metadata_values0_.md">FWPS_INCOMING_METADATA_VALUES0</a> structure.


  
  




## -see-also

<a href="..\fwpsk\ns-fwpsk-fwps_incoming_metadata_values0_.md">FWPS_INCOMING_METADATA_VALUES0</a>



<a href="..\fwpsk\nf-fwpsk-fwpsdereferencevswitchpacketcontext0.md">FwpsDereferencevSwitchPacketContext0</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsReferencevSwitchPacketContext0 function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

