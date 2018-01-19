---
UID: NE:fwpsk.FWPS_FIELDS_RPC_EP_ADD_
title: FWPS_FIELDS_RPC_EP_ADD_
author: windows-driver-content
description: The FWPS_FIELDS_RPC_EP_ADD enumeration type specifies the data field identifiers for the FWPS_LAYER_RPC_EP_ADD run-time filtering layer.
old-location: netvista\fwps_fields_rpc_ep_add.htm
old-project: netvista
ms.assetid: 9062fe5f-4384-4466-a15f-c62f2f429699
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: FWPS_FIELDS_RPC_EP_ADD_, FWPS_FIELDS_RPC_EP_ADD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FWPS_FIELDS_RPC_EP_ADD
req.alt-loc: fwpsk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: FWPS_FIELDS_RPC_EP_ADD
---

# FWPS_FIELDS_RPC_EP_ADD_ enumeration



## -description
The FWPS_FIELDS_RPC_EP_ADD enumeration type specifies the data field identifiers for the
  FWPS_LAYER_RPC_EP_ADD 
  <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa366492">run-time filtering layer</a>.



## -syntax

````
typedef enum FWPS_FIELDS_RPC_EP_ADD_ { 
  FWPS_FIELD_RPC_EP_ADD_PROCESS_WITH_RPC_IF_UUID,
  FWPS_FIELD_RPC_EP_ADD_PROTOCOL,
  FWPS_FIELD_RPC_EP_ADD_EP_VALUE,
  FWPS_FIELD_RPC_EP_ADD_EP_FLAGS,
  FWPS_FIELD_RPC_EP_ADD_MAX
} FWPS_FIELDS_RPC_EP_ADD;
````


## -enum-fields

### -field FWPS_FIELD_RPC_EP_ADD_PROCESS_WITH_RPC_IF_UUID

The UUID of the process with the RPC interface.


### -field FWPS_FIELD_RPC_EP_ADD_PROTOCOL


### -field The RPC protocol. The possible condition values are:
     

### -field RPC_PROTSEQ_TCP
     

### -field RPC_PROTSEQ_HTTP
     

### -field RPC_PROTSEQ_NMP


### -field FWPS_FIELD_RPC_EP_ADD_EP_VALUE

Reserved for internal use.


### -field FWPS_FIELD_RPC_EP_ADD_EP_FLAGS

Reserved for internal use.


### -field FWPS_FIELD_RPC_EP_ADD_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks
