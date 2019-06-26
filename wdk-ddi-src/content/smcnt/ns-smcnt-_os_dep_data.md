---
UID: NS:smcnt._OS_DEP_DATA
title: _OS_DEP_DATA (smcnt.h)
description: The OS_DEP_DATA structure defines the data that is stored in the OsData member of the SMARTCARD_EXTENSION structure, which holds smart card information that is specific to the operating system.
old-location: smartcrd\os_dep_data__wdm_.htm
tech.root: smartcrd
ms.assetid: 76f6f0d1-cb2f-4cda-aeb0-7421e18e3c27
ms.date: 02/22/2018
ms.keywords: "*POS_DEP_DATA, OS_DEP_DATA, OS_DEP_DATA (WDM), OS_DEP_DATA (WDM) structure [Smart Card Reader Devices], OS_DEP_DATA structure [Smart Card Reader Devices], POS_DEP_DATA, POS_DEP_DATA structure pointer [Smart Card Reader Devices], _OS_DEP_DATA, scstruct_f7288ef8-a011-44c0-ab86-db7cc6d1a985.xml, smartcrd.os_dep_data__wdm_, smcnt/OS_DEP_DATA, smcnt/POS_DEP_DATA"
ms.topic: struct
req.header: smcnt.h
req.include-header: Smcnt.h
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
- smcnt.h
api_name:
- OS_DEP_DATA
product:
- Windows
targetos: Windows
req.typenames: OS_DEP_DATA, *POS_DEP_DATA
---

# _OS_DEP_DATA structure


## -description


The OS_DEP_DATA structure defines the data that is stored in the <b>OsData</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/smclib/ns-smclib-_smartcard_extension">SMARTCARD_EXTENSION</a> structure, which holds smart card information that is specific to the operating system. 


## -struct-fields




### -field DeviceObject

A pointer to the smart card reader device object. (Must be set by the driver.)


### -field CurrentIrp

A pointer to the current IRP to process. Access to this field must be sequentialized by using the spin lock pointed to by the <b>OsData->SpinLock</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/smclib/ns-smclib-_smartcard_extension">SMARTCARD_EXTENSION</a>. 


### -field NotificationIrp

A pointer to an IRP that the smart card reader driver uses to notify applications when a smart card has been inserted or removedl. Access to this field must be sequentialized by using the spin lock that is pointed to by the <b>OsData->SpinLock</b> member of SMARTCARD_EXTENSION.  


### -field Mutex

Contains a mutex that applications use to synchronize access to the reader driver. 


### -field SpinLock

Contains a mutex that drivers use to synchronize access to protected members of the OS_DEP_DATA structure. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/smclib/ns-smclib-_scard_card_capabilities">SCARD_CARD_CAPABILITIES</a>.


### -field RemoveLock

A structure with the following members:


### -field RemoveLock.Removed

If this Boolean value is non-zero, it indicates that the spin lock was removed.


### -field RemoveLock.RefCount

If this long integer is non-zero, it indicates the number of references to the spin lock that are currently active. 


### -field RemoveLock.RemoveEvent

A pointer to an event that synchronizes spin lock removal.


### -field RemoveLock.TagList

A pointer to a linked list of structures, each of which contains a tag string that identifies a remove spin lock. 


### -field DebugDeviceObject

Unused.


## -remarks



To allocate this structure, drivers must call <a href="https://docs.microsoft.com/previous-versions/ff548944(v=vs.85)">SmartcardInitialize (WDM)</a>. After this call, drivers should copy the pointer of the smart card device object to <b>DeviceObject</b>. Otherwise, the smart card driver library will not work. Do not use this structure to store driver-dependent information. However, when the smart card driver library calls one of your driver's callback functions, it sets <b>CurrentIrp</b> to the requesting IRP, unless the request is a smart card tracking request. For smart card tracking requests, the driver library sets <b>NotificationIrp</b> to the requesting IRP. For more information about smart card tracking, see <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff548920(v=vs.85)">RDF_CARD_TRACKING</a>.



