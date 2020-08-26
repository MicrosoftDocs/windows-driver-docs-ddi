---
UID: NS:iscsiprf._MSiSCSI_InitiatorInstanceStatistics
title: _MSiSCSI_InitiatorInstanceStatistics (iscsiprf.h)
description: The MSiSCSI_InitiatorInstanceStatistics structure is used by iSCSI initiators to report initiator statistics.
old-location: storage\msiscsi_initiatorinstancestatistics.htm
tech.root: storage
ms.assetid: b07b8186-970a-428f-955f-4e7e6ab20bfc
ms.date: 03/29/2018
keywords: ["MSiSCSI_InitiatorInstanceStatistics structure"]
ms.keywords: "*PMSiSCSI_InitiatorInstanceStatistics, MSiSCSI_InitiatorInstanceStatistics, MSiSCSI_InitiatorInstanceStatistics structure [Storage Devices], PMSiSCSI_InitiatorInstanceStatistics, PMSiSCSI_InitiatorInstanceStatistics structure pointer [Storage Devices], _MSiSCSI_InitiatorInstanceStatistics, iscsiprf/MSiSCSI_InitiatorInstanceStatistics, iscsiprf/PMSiSCSI_InitiatorInstanceStatistics, storage.msiscsi_initiatorinstancestatistics, structs-iSCSI_6914e221-73b2-4626-9281-2e1748bd0048.xml"
f1_keywords:
 - "iscsiprf/MSiSCSI_InitiatorInstanceStatistics"
 - "MSiSCSI_InitiatorInstanceStatistics"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- iscsiprf.h
api_name:
- MSiSCSI_InitiatorInstanceStatistics
targetos: Windows
req.typenames: MSiSCSI_InitiatorInstanceStatistics, *PMSiSCSI_InitiatorInstanceStatistics
---

# _MSiSCSI_InitiatorInstanceStatistics structure


## -description


The MSiSCSI_InitiatorInstanceStatistics structure is used by iSCSI initiators to report initiator statistics.


## -struct-fields




### -field UniqueAdapterId

A 64-bit integer that uniquely identifies an HBA initiator and a loaded instance of a storage miniport driver that manages the HBA. The initiator should use the address of the adapter extension or another address that the device driver owns to construct this identifier (ID). The initiator reports this value in the <b>UniqueAdapterId</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsimgt/ns-iscsimgt-_msiscsi_hbainformation">MSiSCSI_HBAInformation</a> structure. For more information about the class that generates MSiSCSI_HBAInformation, see  <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msiscsi-hbainformation-wmi-class">MSiSCSI_HBAInformation WMI Class</a>.


### -field SessionDigestErrorCount

The number of session digest errors.


### -field SessionConnectionTimeoutErrorCount

The number of session connection time-out errors.


### -field SessionFormatErrorCount

The number of session format errors.


### -field SessionFailureCount

The number of failed sessions that belong to the initiator instance that <b>UniqueAdapterId</b> specifies.


## -remarks



It is optional that you implement this class.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsimgt/ns-iscsimgt-_msiscsi_hbainformation">MSiSCSI_HBAInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msiscsi-hbainformation-wmi-class">MSiSCSI_HBAInformation WMI Class</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msiscsi-initiatorinstancestatistics-wmi-class">MSiSCSI_InitiatorInstanceStatistics WMI Class</a>
 

 

