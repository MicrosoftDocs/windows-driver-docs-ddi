---
UID: NS:iscsimgt._MSiSCSI_PortalInfoClass
title: "_MSiSCSI_PortalInfoClass"
author: windows-driver-content
description: The MSiSCSI_PortalInfoClass structure contains information about a collection of iSCSI portals.
old-location: storage\msiscsi_portalinfoclass.htm
old-project: storage
ms.assetid: 400ff6fc-6eb7-4b3f-afec-7d0b69039ed1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PMSiSCSI_PortalInfoClass, MSiSCSI_PortalInfoClass, MSiSCSI_PortalInfoClass structure [Storage Devices], PMSiSCSI_PortalInfoClass, PMSiSCSI_PortalInfoClass structure pointer [Storage Devices], _MSiSCSI_PortalInfoClass, iscsimgt/MSiSCSI_PortalInfoClass, iscsimgt/PMSiSCSI_PortalInfoClass, storage.msiscsi_portalinfoclass, structs-iSCSI_dec2f67f-5b12-4432-8c64-eef6efeb7e6a.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsimgt.h
req.include-header: Iscsimgt.h
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
-	iscsimgt.h
api_name:
-	MSiSCSI_PortalInfoClass
product: Windows
targetos: Windows
req.typenames: MSiSCSI_PortalInfoClass, *PMSiSCSI_PortalInfoClass
---

# _MSiSCSI_PortalInfoClass structure


## -description


The MSiSCSI_PortalInfoClass structure contains information about a collection of iSCSI portals.


## -syntax


````
typedef struct _MSiSCSI_PortalInfoClass {
  ULONG            PortalInfoCount;
  ISCSI_PortalInfo PortalInformation[1];
} MSiSCSI_PortalInfoClass, *PMSiSCSI_PortalInfoClass;
````


## -struct-fields




### -field PortalInfoCount

The number of portals that the initiator discovered and for which portal information is available.


### -field PortalInformation

A variable length array of <a href="..\iscsimgt\ns-iscsimgt-_iscsi_portalinfo.md">ISCSI_PortalInfo</a> structures. The number of elements in the array is specified by the <b>PortalInfoCount</b> field.


## -remarks



We recommend that you implement this class.




## -see-also

<a href="..\iscsimgt\ns-iscsimgt-_iscsi_portalinfo.md">ISCSI_PortalInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563100">MSiSCSI_PortalInfoClass WMI Class</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSiSCSI_PortalInfoClass structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

