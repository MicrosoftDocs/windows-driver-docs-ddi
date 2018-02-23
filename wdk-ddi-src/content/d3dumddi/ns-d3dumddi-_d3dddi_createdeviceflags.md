---
UID: NS:d3dumddi._D3DDDI_CREATEDEVICEFLAGS
title: "_D3DDDI_CREATEDEVICEFLAGS"
author: windows-driver-content
description: The D3DDDI_CREATEDEVICEFLAGS structure describes how to create a device.
old-location: display\d3dddi_createdeviceflags.htm
old-project: display
ms.assetid: f9415dc9-352a-4e93-a0c1-2519c8c89762
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: D3DDDI_CREATEDEVICEFLAGS, d3dumddi/D3DDDI_CREATEDEVICEFLAGS, D3D_other_Structs_45151acf-e91a-454b-be32-b7b7aaa619e9.xml, display.d3dddi_createdeviceflags, D3DDDI_CREATEDEVICEFLAGS structure [Display Devices], _D3DDDI_CREATEDEVICEFLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3dumddi.h
apiname:
-	D3DDDI_CREATEDEVICEFLAGS
product: Windows
targetos: Windows
req.typenames: D3DDDI_CREATEDEVICEFLAGS
---

# _D3DDDI_CREATEDEVICEFLAGS structure


## -description


The D3DDDI_CREATEDEVICEFLAGS structure describes how to create a device.


## -syntax


````
typedef struct _D3DDDI_CREATEDEVICEFLAGS {
  union {
    struct {
      UINT AllowMultithreading  :1;
      UINT AllowFlipBatching  :1;
      UINT Reserved  :30;
    };
    UINT   Value;
  };
} D3DDDI_CREATEDEVICEFLAGS;
````


## -struct-fields




### -field AllowMultithreading

A UINT value that specifies whether the user-mode display driver can run multiple threads simultaneously when it processes calls to its functions from the Microsoft Direct3D runtime. For situations where the driver must disable multi-threading even when <b>AllowMultithreading</b> is set, see <a href="https://msdn.microsoft.com/906d6b31-a447-4a94-b1a5-cd3028722db7">Supporting Multiple Processors</a>. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field AllowFlipBatching

A UINT value that specifies whether the user-mode display driver can queue flip operation requests so the driver can process them later on another thread. This flag applies only to when a driver implements its own threading. In this situation, the driver is not required to immediately call the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_presentcb.md">pfnPresentCb</a> function when its <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_present.md">Present</a> function is called. 

The Direct3D runtime enforces a queued present limit (currently set to 1) to ensure that frame latency stays at a reasonable level. If an application initiates a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_present.md">Present</a> function while another present operation is queued, the current version of the runtime will flush the queued present. However, drivers should not rely on this behavior because the queued present limit might change in future versions of the runtime.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 30 bits (0xFFFFFFFD) of the 32-bit <b>Value</b> member to zeros.


#### - Value

A member in the union that is contained in D3DDDI_CREATEDEVICEFLAGS that can hold one 32-bit value that identifies how to create the device.


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdevice.md">CreateDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_CREATEDEVICEFLAGS structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

