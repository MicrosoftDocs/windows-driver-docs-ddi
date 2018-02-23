---
UID: NS:iscsiop._MSiSCSI_BootInformation
title: "_MSiSCSI_BootInformation"
author: windows-driver-content
description: The MSiSCSI_BootInformation structure is used with the MSiSCSI_BootInformation WMI Class to expose information about the node that contains the target boot device.
old-location: storage\msiscsi_bootinformation.htm
old-project: storage
ms.assetid: 971bbd30-5bde-4cf6-9b94-7c21c29590d5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: iscsiop/PMSiSCSI_BootInformation, MSiSCSI_BootInformation structure [Storage Devices], storage.msiscsi_bootinformation, PMSiSCSI_BootInformation, PMSiSCSI_BootInformation structure pointer [Storage Devices], MSiSCSI_BootInformation, structs-iSCSI_a33678de-f559-4c7a-8007-55ab0381b613.xml, _MSiSCSI_BootInformation, *PMSiSCSI_BootInformation, iscsiop/MSiSCSI_BootInformation
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
-	MSiSCSI_BootInformation
product: Windows
targetos: Windows
req.typenames: MSiSCSI_BootInformation, *PMSiSCSI_BootInformation
---

# _MSiSCSI_BootInformation structure


## -description


The MSiSCSI_BootInformation structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562984">MSiSCSI_BootInformation WMI Class</a> to expose information about the node that contains the target boot device. 


## -syntax


````
typedef struct _MSiSCSI_BootInformation {
  UCHAR NodeName[223];
  ULONG SharedSecretLength;
  UCHAR SharedSecret[255];
} MSiSCSI_BootInformation, *PMSiSCSI_BootInformation;
````


## -struct-fields




### -field NodeName

The name of the initiator node that contains the boot device.


### -field SharedSecretLength

The length, in bytes, of the shared secret for the initiator node.


### -field SharedSecret

The shared secret for the initiator node.


## -remarks



You must implement this class if the adapter supports iSCSI boot.




## -see-also

<a href="https://msdn.microsoft.com/a6ed673a-b5c1-4857-803a-4f0f3cf798d8">MSiSCSI_BootInformationWMI Class</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSiSCSI_BootInformation structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

