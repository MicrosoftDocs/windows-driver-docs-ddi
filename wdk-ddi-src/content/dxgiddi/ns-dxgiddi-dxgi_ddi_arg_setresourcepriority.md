---
UID: NS:dxgiddi.DXGI_DDI_ARG_SETRESOURCEPRIORITY
title: DXGI_DDI_ARG_SETRESOURCEPRIORITY
author: windows-driver-content
description: The DXGI_DDI_ARG_SETRESOURCEPRIORITY structure describes parameters for setting the priority level of a resource.
old-location: display\dxgi_ddi_arg_setresourcepriority.htm
old-project: display
ms.assetid: 9d3f5687-bc49-4831-bf56-5d4201ed45de
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, A, C, D, DXGI_DDI_ARG_SETRESOURCEPRIORITY, DXGI_DDI_ARG_SETRESOURCEPRIORITY structure [Display Devices], E, G, I, O, P, R, S, T, U, UMDisplayDriver_Dx10param_Structs_fda8895f-9cc7-496b-ae2e-bf6b076fc0b3.xml, X, Y, _, display.dxgi_ddi_arg_setresourcepriority, dxgiddi/DXGI_DDI_ARG_SETRESOURCEPRIORITY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
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
-	dxgiddi.h
apiname:
-	DXGI_DDI_ARG_SETRESOURCEPRIORITY
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_SETRESOURCEPRIORITY
---

# DXGI_DDI_ARG_SETRESOURCEPRIORITY structure


## -description


The DXGI_DDI_ARG_SETRESOURCEPRIORITY structure describes parameters for setting the priority level of a resource. 


## -syntax


````
typedef struct DXGI_DDI_ARG_SETRESOURCEPRIORITY {
  DXGI_DDI_HDEVICE   hDevice;
  DXGI_DDI_HRESOURCE hResource;
  UINT               Priority;
} DXGI_DDI_ARG_SETRESOURCEPRIORITY;
````


## -struct-fields




### -field hDevice

[in] A handle to the display device (graphics context) on which the driver sets the eviction-from-memory priority for a resource. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function to create the display device. 


### -field hResource

[in] A handle to the resource to set the priority level for.


### -field Priority

[in] The priority level to set for the resource that the <b>hResource</b> member specifies. A resource's priority level can be set anywhere in the range from 0 through 0xFFFFFFFF.


## -remarks



The priority level that a resource is set at determines its eviction order from memory. A resource that is assigned a low priority is evicted before a resource with a high priority. If two resources have the same priority, the resource that was used more recently is kept in memory; the other resource is evicted.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569657">SetResourcePriorityDXGI</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_ARG_SETRESOURCEPRIORITY structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

