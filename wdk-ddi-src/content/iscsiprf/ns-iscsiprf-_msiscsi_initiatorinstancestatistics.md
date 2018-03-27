---
UID: NS:iscsiprf._MSiSCSI_InitiatorInstanceStatistics
title: "_MSiSCSI_InitiatorInstanceStatistics"
author: windows-driver-content
description: The MSiSCSI_InitiatorInstanceStatistics structure is used by iSCSI initiators to report initiator statistics.
old-location: storage\msiscsi_initiatorinstancestatistics.htm
old-project: storage
ms.assetid: b07b8186-970a-428f-955f-4e7e6ab20bfc
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PMSiSCSI_InitiatorInstanceStatistics, MSiSCSI_InitiatorInstanceStatistics, MSiSCSI_InitiatorInstanceStatistics structure [Storage Devices], PMSiSCSI_InitiatorInstanceStatistics, PMSiSCSI_InitiatorInstanceStatistics structure pointer [Storage Devices], _MSiSCSI_InitiatorInstanceStatistics, iscsiprf/MSiSCSI_InitiatorInstanceStatistics, iscsiprf/PMSiSCSI_InitiatorInstanceStatistics, storage.msiscsi_initiatorinstancestatistics, structs-iSCSI_6914e221-73b2-4626-9281-2e1748bd0048.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iscsiprf.h
api_name:
-	MSiSCSI_InitiatorInstanceStatistics
product: Windows
targetos: Windows
req.typenames: MSiSCSI_InitiatorInstanceStatistics, *PMSiSCSI_InitiatorInstanceStatistics
---

# _MSiSCSI_InitiatorInstanceStatistics structure


## -description


The MSiSCSI_InitiatorInstanceStatistics structure is used by iSCSI initiators to report initiator statistics.


## -struct-fields




### -field UniqueAdapterId

A 64-bit integer that uniquely identifies an HBA initiator and a loaded instance of a storage miniport driver that manages the HBA. The initiator should use the address of the adapter extension or another address that the device driver owns to construct this identifier (ID). The initiator reports this value in the <b>UniqueAdapterId</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563012">MSiSCSI_HBAInformation</a> structure. For more information about the class that generates MSiSCSI_HBAInformation, see  <a href="https://msdn.microsoft.com/library/windows/hardware/ff563017">MSiSCSI_HBAInformation WMI Class</a>.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563012">MSiSCSI_HBAInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563017">MSiSCSI_HBAInformation WMI Class</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563038">MSiSCSI_InitiatorInstanceStatistics WMI Class</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSiSCSI_InitiatorInstanceStatistics structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

