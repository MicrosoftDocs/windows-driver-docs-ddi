---
UID: NS:ntddscsi._SCSI_BUS_DATA
title: _SCSI_BUS_DATA
author: windows-driver-content
description: The SCSI_BUS_DATA structure is used in conjunction with the IOCTL_SCSI_GET_INQUIRY_DATA request and the SCSI_ADAPTER_BUS_INFO structure to retrieve the SCSI inquiry data for all devices on a given SCSI bus.
old-location: storage\scsi_bus_data.htm
old-project: storage
ms.assetid: d7baddb5-ad12-4aea-9515-97511dc05fe7
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _SCSI_BUS_DATA, SCSI_BUS_DATA, *PSCSI_BUS_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SCSI_BUS_DATA
req.alt-loc: ntddscsi.h
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
req.typenames: SCSI_BUS_DATA, *PSCSI_BUS_DATA
---

# _SCSI_BUS_DATA structure



## -description
The SCSI_BUS_DATA structure is used in conjunction with the <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_get_inquiry_data.md">IOCTL_SCSI_GET_INQUIRY_DATA</a> request and the <a href="..\ntddscsi\ns-ntddscsi-_scsi_adapter_bus_info.md">SCSI_ADAPTER_BUS_INFO</a> structure to retrieve the SCSI inquiry data for all devices on a given SCSI bus. 



## -syntax

````
typedef struct _SCSI_BUS_DATA {
  UCHAR NumberOfLogicalUnits;
  UCHAR InitiatorBusId;
  ULONG InquiryDataOffset;
} SCSI_BUS_DATA, *PSCSI_BUS_DATA;
````


## -struct-fields

### -field NumberOfLogicalUnits

Contains the number of logical units on the bus for which inquiry data is being retrieved. 


### -field InitiatorBusId

Contains the SCSI bus ID for the adapter. 


### -field InquiryDataOffset

Contains an offset from the beginning of the SCSI_ADAPTER_BUS_INFO structure to the inquiry data.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_get_inquiry_data.md">IOCTL_SCSI_GET_INQUIRY_DATA</a>
</dt>
<dt>
<a href="..\ntddscsi\ns-ntddscsi-_scsi_adapter_bus_info.md">SCSI_ADAPTER_BUS_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SCSI_BUS_DATA structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

