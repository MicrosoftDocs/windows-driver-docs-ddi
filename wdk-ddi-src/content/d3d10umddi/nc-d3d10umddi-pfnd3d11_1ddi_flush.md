---
UID: NC:d3d10umddi.PFND3D11_1DDI_FLUSH
title: PFND3D11_1DDI_FLUSH
author: windows-driver-content
description: Submits outstanding hardware commands that are in the hardware command buffer to the display miniport driver. Implemented by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\flush_d3d11_1_.htm
old-project: display
ms.assetid: 6f4bda19-2d51-4058-ba68-cbb5deb44a54
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.flush_d3d11_1_, Flush(D3D11_1) callback function [Display Devices], Flush(D3D11_1), PFND3D11_1DDI_FLUSH, PFND3D11_1DDI_FLUSH, d3d10umddi/Flush(D3D11_1)
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	UserDefined
apilocation:
-	d3d10umddi.h
apiname:
-	Flush(D3D11_1)
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D11_1DDI_FLUSH callback


## -description


Submits outstanding hardware commands that are in the hardware command buffer to the display miniport driver. Implemented by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.


## -prototype


````
PFND3D11_1DDI_FLUSH Flush(D3D11_1);

BOOL APIENTRY* Flush(D3D11_1)(
  _In_ D3D10DDI_HDEVICE hDevice,
  _In_ UINT             FlushFlags
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



#### - FlushFlags [in]

 A value from the <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1_ddi_flush_flags.md">D3D11_1_DDI_FLUSH_FLAGS</a> enumeration that indicates whether the driver should  continue to submit command buffers if there have been no new commands.


#### - hDevice [in]

 A handle to the display device (graphics context).


## -returns


Returns <b>TRUE</b> if the hardware commands were successfully flushed. Otherwise returns <b>FALSE</b>.



## -remarks


After the <i>Flush(D3D11_1)</i> function completes, all previously issued commands no longer depend on actions that occur within the application's user-mode context. In addition, applications can safely suspend themselves without blocking rendering until the kernel restarts them (such as, when an asynchronous query is used).

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>Flush(D3D11_1)</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_1ddi_devicefuncs.md">D3D10_1DDI_DEVICEFUNCS</a>

<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1_ddi_flush_flags.md">D3D11_1_DDI_FLUSH_FLAGS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_FLUSH callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

