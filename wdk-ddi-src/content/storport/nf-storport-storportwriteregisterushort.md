---
UID: NF:storport.StorPortWriteRegisterUshort
title: StorPortWriteRegisterUshort macro
author: windows-driver-content
description: The StorPortWriteRegisterUshort routine transfers a ULONG value to the indicated HBA register address.
old-location: storage\storportwriteregisterushort.htm
old-project: storage
ms.assetid: f4beff75-6177-40c7-a62c-6e24bc54ea58
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortWriteRegisterUshort routine [Storage Devices], storport/StorPortWriteRegisterUshort, storage.storportwriteregisterushort, storprt_f4cd6932-3fd0-435f-87f3-7241a5778073.xml, StorPortWriteRegisterUshort
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: Storport.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Storport.lib
-	Storport.dll
apiname:
-	StorPortWriteRegisterUshort
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortWriteRegisterUshort macro


## -description


The <b>StorPortWriteRegisterUshort</b> routine transfers a ULONG value to the indicated HBA register address.


## -syntax


````
STORPORT_API VOID StorPortWriteRegisterUshort(
  _In_ PVOID   HwDeviceExtension,
  _In_ PUSHORT Register,
  _In_ USHORT  Value
);
````


## -parameters




### -param h

TBD


### -param r

TBD


### -param v

TBD






#### - HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 


#### - Register [in]

Pointer to the register. The given <i>Register</i> must be in a mapped memory space range returned by <a href="..\storport\nf-storport-storportgetdevicebase.md">StorPortGetDeviceBase</a>. 


#### - Value [in]

Specifies the USHORT value to be written to the HBA's register.


## -see-also

<a href="..\srb\nf-srb-scsiportwriteregisterushort.md">ScsiPortWriteRegisterUshort</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortWriteRegisterUshort routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

