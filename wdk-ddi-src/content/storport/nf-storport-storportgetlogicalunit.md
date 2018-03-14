---
UID: NF:storport.StorPortGetLogicalUnit
title: StorPortGetLogicalUnit function
author: windows-driver-content
description: The StorPortGetLogicalUnit routine returns a pointer to the miniport driver's per-logical-unit storage area.
old-location: storage\storportgetlogicalunit.htm
old-project: storage
ms.assetid: c8972d8b-9eba-4276-af63-1096a76b104f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortGetLogicalUnit, StorPortGetLogicalUnit routine [Storage Devices], storage.storportgetlogicalunit, storport/StorPortGetLogicalUnit, storprt_065c9617-06c6-4795-9743-14cd5803d9f9.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
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
req.lib: Storport.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Storport.lib
-	Storport.dll
api_name:
-	StorPortGetLogicalUnit
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortGetLogicalUnit function


## -description


The <b>StorPortGetLogicalUnit</b> routine returns a pointer to the miniport driver's per-logical-unit storage area.


## -syntax


````
STORPORT_API PVOID StorPortGetLogicalUnit(
  _In_ PVOID HwDeviceExtension,
  _In_ UCHAR PathId,
  _In_ UCHAR TargetId,
  _In_ UCHAR Lun
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver as soon as the miniport driver's <a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a> routine is called. The port driver frees this memory when it removes the device. 


### -param PathId [in]

Identifies the SCSI bus. 


### -param TargetId [in]

Identifies the target controller or device on the bus. 


### -param Lun [in]

Identifies the logical unit (LU) number of the target device. 


## -returns



<b>StorPortGetLogicalUnit</b> returns a pointer to the miniport driver's storage area for the requested logical unit. If the logical unit does not exist, it returns <b>NULL</b>.




## -remarks



<b>StorPortGetLogicalUnit</b> is irrelevant if the miniport driver's <a href="..\wudfwdm\nc-wudfwdm-driver_initialize.md">DriverEntry</a> routine specified zero for the <b>LuExtensionSize</b> in the <a href="..\strmini\ns-strmini-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a> when it called <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. Otherwise, the operating system-specific port driver allocates and initializes with zeros a set of LU extensions of the specified size for the miniport driver to use.

Per-LU storage can be used to store data relevant to a particular peripheral, such as saved data pointers. To access this area, the miniport driver calls <b>StorPortGetLogicalUnit</b> when the driver is maintaining information about the state of or current operation for any particular peripheral.

The operating system-specific port driver can consider a logical unit to be nonexistent if there is no active request for that logical unit and the device has never been successfully selected.

<div class="alert"><b>Note</b>  When the miniport driver calls <b>StorPortGetLogicalUnit</b> at IRQL = DISPATCH_LEVEL, the function acquires the interrupt lock. Calling <b>StorPortGetLogicalUnit</b> too often at this IRQL level impacts the performance and scalability of the miniport driver.</div>
<div> </div>



## -see-also

<a href="..\strmini\ns-strmini-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a>



<a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortGetLogicalUnit routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

