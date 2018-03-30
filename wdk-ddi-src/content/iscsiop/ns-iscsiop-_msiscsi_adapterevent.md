---
UID: NS:iscsiop._MSiSCSI_AdapterEvent
title: "_MSiSCSI_AdapterEvent"
author: windows-driver-content
description: The MSiSCSI_AdapterEvent structure contains information that is reported whenever an adapter event occurs.
old-location: storage\msiscsi_adapterevent.htm
old-project: storage
ms.assetid: 03820d4d-d013-40fb-a686-1b228f178f50
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PMSiSCSI_AdapterEvent, MSiSCSI_AdapterEvent, MSiSCSI_AdapterEvent structure [Storage Devices], PMSiSCSI_AdapterEvent, PMSiSCSI_AdapterEvent structure pointer [Storage Devices], _MSiSCSI_AdapterEvent, iscsiop/MSiSCSI_AdapterEvent, iscsiop/PMSiSCSI_AdapterEvent, storage.msiscsi_adapterevent, structs-iSCSI_86ec7324-3d5c-44d2-8972-691504f1c5e1.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iscsiop.h
api_name:
-	MSiSCSI_AdapterEvent
product: Windows
targetos: Windows
req.typenames: MSiSCSI_AdapterEvent, *PMSiSCSI_AdapterEvent
---

# _MSiSCSI_AdapterEvent structure


## -description


The MSiSCSI_AdapterEvent structure contains information that is reported whenever an adapter event occurs.


## -struct-fields




### -field UniqueAdapterId

A 64-bit integer that uniquely identifies an HBA initiator and a loaded instance of a storage miniport driver that manages the HBA. The initiator should use the address of the adapter extension or another address that the device driver owns to construct this identifier (ID). The initiator reports this value in the <b>UniqueAdapterId</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563012">MSiSCSI_HBAInformation</a> structure.


### -field EventCode

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff561485">ISCSI_ADAPTER_EVENT_CODE</a> enumeration value that indicates the type of adapter event that occurred.


## -remarks



The WMI tool suite automatically generates a declaration of the MSiSCSI_AdapterEvent structure when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562971">MSiSCSI_AdapterEvent WMI Class</a> in <i>Operations.mof</i>.  You must implement this method if the adapter supports discovery.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561485">ISCSI_ADAPTER_EVENT_CODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562971">MSiSCSI_AdapterEvent WMI Class</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563012">MSiSCSI_HBAInformation</a>
 

 

