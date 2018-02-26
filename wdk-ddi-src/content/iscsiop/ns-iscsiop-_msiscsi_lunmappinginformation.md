---
UID: NS:iscsiop._MSiSCSI_LUNMappingInformation
title: "_MSiSCSI_LUNMappingInformation"
author: windows-driver-content
description: This MSiSCSI_LUNMappingInformation structure provides the SCSI address information that the operating system assigns to a particular logical unit.
old-location: storage\msiscsi_lunmappinginformation.htm
old-project: storage
ms.assetid: abe4b0fe-3918-4139-9c35-d9399287ce03
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PMSiSCSI_LUNMappingInformation, ,, C, I, L, M, MSiSCSI_LUNMappingInformation, MSiSCSI_LUNMappingInformation structure [Storage Devices], N, P, PMSiSCSI_LUNMappingInformation, PMSiSCSI_LUNMappingInformation structure pointer [Storage Devices], S, U, _, _MSiSCSI_LUNMappingInformation, a, f, g, i, iscsiop/MSiSCSI_LUNMappingInformation, iscsiop/PMSiSCSI_LUNMappingInformation, m, n, o, p, r, storage.msiscsi_lunmappinginformation, structs-iSCSI_390283b1-22d6-4012-834f-1b3ef3328da0.xml, t"
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
-	MSiSCSI_LUNMappingInformation
product: Windows
targetos: Windows
req.typenames: MSiSCSI_LUNMappingInformation, *PMSiSCSI_LUNMappingInformation
---

# _MSiSCSI_LUNMappingInformation structure


## -description


This MSiSCSI_LUNMappingInformation structure provides the SCSI address information that the operating system assigns to a particular logical unit.


## -syntax


````
typedef struct _MSiSCSI_LUNMappingInformation {
  ULONGLONG UniqueAdapterId;
  ULONGLONG UniqueSessionId;
  ULONG     OSBus;
  ULONG     OSTarget;
  ULONG     OSLUN;
} MSiSCSI_LUNMappingInformation, *PMSiSCSI_LUNMappingInformation;
````


## -struct-fields




### -field UniqueAdapterId

A 64-bit integer that uniquely identifies an HBA initiator and a loaded instance of a storage miniport driver that manages the HBA. The initiator should use the address of the adapter extension or another address that the device driver owns to construct this identifier (ID). The initiator reports this value in the <b>UniqueAdapterId</b> member of the <a href="..\iscsimgt\ns-iscsimgt-_msiscsi_hbainformation.md">MSiSCSI_HBAInformation</a> structure.


### -field UniqueSessionId

A session ID that uniquely identifies the session for which the LUN mapping is valid. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> methods both return this value in the <i>UniqueSessionId</i> parameter. Do not confuse this value with the values in the ISID and TSID members.


### -field OSBus

The number that the operating system assigns to the bus that the adapter is attached to.


### -field OSTarget

The device number that the operating system assigns to the target.


### -field OSLUN

The logical unit number (LUN) that the operating system assigns to the logical unit.


## -remarks



You must implement this class.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>



<a href="..\iscsiop\ns-iscsiop-_msiscsi_targetmappings.md">MSiSCSI_TargetMappings</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563067">MSiSCSI_LUNMappingInformation WMI Class</a>



<a href="..\iscsimgt\ns-iscsimgt-_msiscsi_hbainformation.md">MSiSCSI_HBAInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSiSCSI_LUNMappingInformation structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

