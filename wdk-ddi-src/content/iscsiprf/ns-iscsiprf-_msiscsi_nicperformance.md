---
UID: NS:iscsiprf._MSiSCSI_NICPerformance
title: _MSiSCSI_NICPerformance (iscsiprf.h)
description: The MSiSCSI_NICPerformance structure can be used by an iSCSI initiator to report statistics for a network interface card (NIC) port.
old-location: storage\msiscsi_nicperformance.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["MSiSCSI_NICPerformance structure"]
ms.keywords: "*PMSiSCSI_NICPerformance, MSiSCSI_NICPerformance, MSiSCSI_NICPerformance structure [Storage Devices], PMSiSCSI_NICPerformance, PMSiSCSI_NICPerformance structure pointer [Storage Devices], _MSiSCSI_NICPerformance, iscsiprf/MSiSCSI_NICPerformance, iscsiprf/PMSiSCSI_NICPerformance, storage.msiscsi_nicperformance, structs-iSCSI_a4d4dddd-24f6-4aa5-9b2c-61c0f1604fdb.xml"
req.header: iscsiprf.h
req.include-header: Iscsiprf.h
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
req.irql: 
targetos: Windows
req.typenames: MSiSCSI_NICPerformance, *PMSiSCSI_NICPerformance
f1_keywords:
 - _MSiSCSI_NICPerformance
 - iscsiprf/_MSiSCSI_NICPerformance
 - PMSiSCSI_NICPerformance
 - iscsiprf/PMSiSCSI_NICPerformance
 - MSiSCSI_NICPerformance
 - iscsiprf/MSiSCSI_NICPerformance
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsiprf.h
api_name:
 - _MSiSCSI_NICPerformance
 - PMSiSCSI_NICPerformance
 - MSiSCSI_NICPerformance
---

# _MSiSCSI_NICPerformance structure


## -description

The MSiSCSI_NICPerformance structure can be used by an iSCSI initiator to report statistics for a network interface card (NIC) port.

## -struct-fields

### -field BytesTransmitted

The number of bytes that are transmitted through the Ethernet port.

### -field BytesReceived

The number of bytes that are received through the Ethernet port.

### -field PDUTransmitted

The number of PDUs that are transmitted through the Ethernet port.

### -field PDUReceived

The number of PDUs that are received through the Ethernet port.

## -remarks

It is optional that you implement this class.

## -see-also

<a href="/windows-hardware/drivers/storage/msiscsi-nicperformance-wmi-class">MSiSCSI_NICPerformance WMI Class</a>

