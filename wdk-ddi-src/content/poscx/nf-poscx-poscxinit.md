---
UID: NF:poscx.PosCxInit
title: PosCxInit function
author: windows-driver-content
description: PosCxInit is called to initialize the PosCx library's internal resources. The resources are tied to the device, and are released when the device goes away.
old-location: pos\poscxinit.htm
old-project: pos
ms.assetid: 23FEA770-12E1-44EC-901D-5C660F5F054A
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: PosCxInit, PosCxInit function, pos.poscxinit, poscx/PosCxInit
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: poscx.h
req.include-header: Poscx.h
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
-	poscx.h
api_name:
-	PosCxInit
product: Windows
targetos: Windows
req.typenames: POS_CX_EVENT_PRIORITY
req.product: Windows 10 or later.
---

# PosCxInit function


## -description


PosCxInit is called to initialize the PosCx library's internal resources. The resources are tied to the device, and are released when the device goes away.

It is recommended to call this method while handling EvtDeviceAdd.


## -syntax


````
NTSTATUS PosCxInit(
  _In_ WDFDEVICE         device,
  _In_ POS_CX_ATTRIBUTES *posCxAttrPtr
);
````


## -parameters




### -param device [in]

A handle to a framework device object that represents the device.


### -param posCxAttrPtr [in]

A pointer to a caller-allocated and initialized <a href="..\poscx\ns-poscx-_pos_cx_attributes.md">POS_CX_ATTRIBUTES</a> structure. The structure should be initialized with <a href="..\poscx\nf-poscx-pos_cx_attributes_init.md">POS_CX_ATTRIBUTES_INIT</a>.


## -returns



An appropriate NTSTATUS error code that indicates success or failure of the initialization.




## -see-also

<a href="..\poscx\ns-poscx-_pos_cx_attributes.md">POS_CX_ATTRIBUTES</a>



<a href="..\poscx\nf-poscx-pos_cx_attributes_init.md">POS_CX_ATTRIBUTES_INIT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [pos\pos]:%20PosCxInit function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

