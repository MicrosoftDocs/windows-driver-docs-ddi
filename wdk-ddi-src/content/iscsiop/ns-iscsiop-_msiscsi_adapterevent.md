---
UID: NS:iscsiop._MSiSCSI_AdapterEvent
title: "_MSiSCSI_AdapterEvent"
author: windows-driver-content
description: The MSiSCSI_AdapterEvent structure contains information that is reported whenever an adapter event occurs.
old-location: storage\msiscsi_adapterevent.htm
old-project: storage
ms.assetid: 03820d4d-d013-40fb-a686-1b228f178f50
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: structs-iSCSI_86ec7324-3d5c-44d2-8972-691504f1c5e1.xml, _MSiSCSI_AdapterEvent, iscsiop/PMSiSCSI_AdapterEvent, iscsiop/MSiSCSI_AdapterEvent, *PMSiSCSI_AdapterEvent, MSiSCSI_AdapterEvent, MSiSCSI_AdapterEvent structure [Storage Devices], storage.msiscsi_adapterevent, PMSiSCSI_AdapterEvent, PMSiSCSI_AdapterEvent structure pointer [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iscsiop.h
apiname:
-	MSiSCSI_AdapterEvent
product: Windows
targetos: Windows
req.typenames: "*PMSiSCSI_AdapterEvent, MSiSCSI_AdapterEvent"
---

# _MSiSCSI_AdapterEvent structure


## -description


The MSiSCSI_AdapterEvent structure contains information that is reported whenever an adapter event occurs.


## -syntax


````
typedef struct _MSiSCSI_AdapterEvent {
  ULONGLONG UniqueAdapterId;
  ULONG     EventCode;
} MSiSCSI_AdapterEvent, *PMSiSCSI_AdapterEvent;
````


## -struct-fields




### -field UniqueAdapterId

A 64-bit integer that uniquely identifies an HBA initiator and a loaded instance of a storage miniport driver that manages the HBA. The initiator should use the address of the adapter extension or another address that the device driver owns to construct this identifier (ID). The initiator reports this value in the <b>UniqueAdapterId</b> member of the <a href="..\iscsimgt\ns-iscsimgt-_msiscsi_hbainformation.md">MSiSCSI_HBAInformation</a> structure.


### -field EventCode

An <a href="..\iscsiop\ne-iscsiop-piscsi_adapter_event_code.md">ISCSI_ADAPTER_EVENT_CODE</a> enumeration value that indicates the type of adapter event that occurred.


## -remarks



The WMI tool suite automatically generates a declaration of the MSiSCSI_AdapterEvent structure when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562971">MSiSCSI_AdapterEvent WMI Class</a> in <i>Operations.mof</i>.  You must implement this method if the adapter supports discovery.




## -see-also

<a href="..\iscsimgt\ns-iscsimgt-_msiscsi_hbainformation.md">MSiSCSI_HBAInformation</a>



<a href="..\iscsiop\ne-iscsiop-piscsi_adapter_event_code.md">ISCSI_ADAPTER_EVENT_CODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562971">MSiSCSI_AdapterEvent WMI Class</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSiSCSI_AdapterEvent structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

