---
UID: NS:iscsiop._MSiSCSI_LUNMappingInformation
title: _MSiSCSI_LUNMappingInformation (iscsiop.h)
description: This MSiSCSI_LUNMappingInformation structure provides the SCSI address information that the operating system assigns to a particular logical unit.
old-location: storage\msiscsi_lunmappinginformation.htm
tech.root: storage
ms.assetid: abe4b0fe-3918-4139-9c35-d9399287ce03
ms.date: 03/29/2018
ms.keywords: "*PMSiSCSI_LUNMappingInformation, MSiSCSI_LUNMappingInformation, MSiSCSI_LUNMappingInformation structure [Storage Devices], PMSiSCSI_LUNMappingInformation, PMSiSCSI_LUNMappingInformation structure pointer [Storage Devices], _MSiSCSI_LUNMappingInformation, iscsiop/MSiSCSI_LUNMappingInformation, iscsiop/PMSiSCSI_LUNMappingInformation, storage.msiscsi_lunmappinginformation, structs-iSCSI_390283b1-22d6-4012-834f-1b3ef3328da0.xml"
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
-	MSiSCSI_LUNMappingInformation
product:
- Windows
targetos: Windows
req.typenames: MSiSCSI_LUNMappingInformation, *PMSiSCSI_LUNMappingInformation
---

# _MSiSCSI_LUNMappingInformation structure


## -description


This MSiSCSI_LUNMappingInformation structure provides the SCSI address information that the operating system assigns to a particular logical unit.


## -struct-fields




### -field UniqueAdapterId

A 64-bit integer that uniquely identifies an HBA initiator and a loaded instance of a storage miniport driver that manages the HBA. The initiator should use the address of the adapter extension or another address that the device driver owns to construct this identifier (ID). The initiator reports this value in the <b>UniqueAdapterId</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563012">MSiSCSI_HBAInformation</a> structure.


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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563012">MSiSCSI_HBAInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563067">MSiSCSI_LUNMappingInformation WMI Class</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563144">MSiSCSI_TargetMappings</a>
 

 

