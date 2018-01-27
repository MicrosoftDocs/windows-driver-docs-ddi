---
UID: NS:dxgiddi._DXGI_DDI_ARG_RECLAIMRESOURCES
title: _DXGI_DDI_ARG_RECLAIMRESOURCES
author: windows-driver-content
description: Describes video memory resources that are to be reclaimed and that the user-mode display driver previously offered for reuse. Used with the pfnReclaimResources function by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\dxgi_ddi_arg_reclaimresources.htm
old-project: display
ms.assetid: 43e34157-2cf1-4e2c-bcd8-c4425e89fb0f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGI_DDI_ARG_RECLAIMRESOURCES, dxgiddi/DXGI_DDI_ARG_RECLAIMRESOURCES, _DXGI_DDI_ARG_RECLAIMRESOURCES, DXGI_DDI_ARG_RECLAIMRESOURCES structure [Display Devices], display.dxgi_ddi_arg_reclaimresources
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8,WDDM 1.2 and later
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
-	HeaderDef
apilocation: 
-	Dxgiddi.h
apiname: 
-	DXGI_DDI_ARG_RECLAIMRESOURCES
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_RECLAIMRESOURCES
---

# _DXGI_DDI_ARG_RECLAIMRESOURCES structure


## -description


Describes video memory resources that are to be reclaimed and that the user-mode display driver  previously offered  for reuse. Used with the <a href="https://msdn.microsoft.com/AF3DCD16-9F8C-442A-A9A5-9EA2BD1C3B84">pfnReclaimResources</a> function by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.


## -syntax


````
typedef struct _DXGI_DDI_ARG_RECLAIMRESOURCES {
  DXGI_DDI_HDEVICE         hDevice;
  const DXGI_DDI_HRESOURCE *pResources;
  BOOL                     *pDiscarded;
  UINT                     Resources;
} DXGI_DDI_ARG_RECLAIMRESOURCES;
````


## -struct-fields




### -field hDevice

[in] A handle to the display device (graphics context) on which the driver offers resources for reuse.

The Direct3D runtime passed this handle to the driver in the <b>hDrvDevice</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a> structure when it created the device by calling the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> routine.


### -field pResources

[in] A pointer to an array of handles to the resources that are to be reclaimed.


### -field pDiscarded

[out] An optional array of Boolean values that specify whether each resource or allocation was discarded.

Each Boolean value in this array corresponds to a resource at the same index location in the structure pointed to by <b>pResources</b>.

The driver sets each Boolean value to <b>TRUE</b> if the correponding resource was discarded, or to <b>FALSE</b> if not.

If <b>pDiscarded</b> is <b>NULL</b>, the driver can ignore it.


### -field Resources

[in] The number of elements in the arrays pointed to by <b>pResources</b> and <b>pDiscarded</b>.


## -see-also

<a href="https://msdn.microsoft.com/AF3DCD16-9F8C-442A-A9A5-9EA2BD1C3B84">pfnReclaimResources</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_ARG_RECLAIMRESOURCES structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

