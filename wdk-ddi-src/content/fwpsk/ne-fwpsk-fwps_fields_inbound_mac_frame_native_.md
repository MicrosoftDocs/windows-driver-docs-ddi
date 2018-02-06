---
UID: NE:fwpsk.FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE_
title: FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE_
author: windows-driver-content
description: The FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE enumeration type specifies the data field identifiers for the FWPS_LAYER_INBOUND_MAC_FRAME_NATIVE run-time filtering layer.
old-location: netvista\fwps_fields_inbound_mac_frame_native.htm
old-project: netvista
ms.assetid: 0EFD49D5-1A5D-4D8F-AA19-7A1562C4B581
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE_INDEX, FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE_, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_MEDIA_TYPE, FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_PHYSICAL_MEDIA_TYPE, FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_MAX, FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_FLAGS, FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE_TYPE, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_PHYSICAL_MEDIA_TYPE, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_PORT, fwpsk/FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_FLAGS, FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_MEDIA_TYPE, FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_MAX, FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_PORT, netvista.fwps_fields_inbound_mac_frame_native, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE_INDEX, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE_TYPE, FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	fwpsk.h
apiname:
-	FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE
product: Windows
targetos: Windows
req.typenames: FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE
---

# FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE_ enumeration


## -description


The FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE enumeration type specifies the data field identifiers for the
  FWPS_LAYER_INBOUND_MAC_FRAME_NATIVE 
  <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa366492">run-time filtering layer</a>.


## -syntax


````
typedef enum  { 
  FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_MEDIA_TYPE,
  FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_PHYSICAL_MEDIA_TYPE,
  FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE,
  FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE_TYPE,
  FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE_INDEX,
  FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_PORT,
  FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_FLAGS,
  FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_MAX
} FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE;
````


## -enum-fields




### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_MEDIA_TYPE

The inbound MAC frame native NDIS media type field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_PHYSICAL_MEDIA_TYPE

The inbound MAC frame native NDIS physical media type field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE

The inbound MAC frame native interface field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE_TYPE

The inbound MAC frame native interface type field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE_INDEX

The inbound MAC frame native interface index field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_PORT

The inbound MAC frame native NDIS port field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_L2_FLAGS



### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_COMPARTMENT_ID



### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


#### - FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_FLAGS

The inbound MAC frame native flags field.

