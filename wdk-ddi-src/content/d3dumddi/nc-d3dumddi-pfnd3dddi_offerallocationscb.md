---
UID: NC:d3dumddi.PFND3DDDI_OFFERALLOCATIONSCB
title: PFND3DDDI_OFFERALLOCATIONSCB
author: windows-driver-content
description: Called by the user-mode display driver to offer video memory allocations for reuse.
old-location: display\pfnofferallocationscb.htm
old-project: display
ms.assetid: D711C545-BDEE-4EE5-B80A-75F01FAA0C33
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: PFND3DDDI_OFFERALLOCATIONSCB, d3dumddi/pfnOfferAllocationsCb, display.pfnofferallocationscb, pfnOfferAllocationsCb, pfnOfferAllocationsCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
apiname:
-	pfnOfferAllocationsCb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_OFFERALLOCATIONSCB callback


## -description


Called by the user-mode display driver   to offer  video memory allocations for reuse.


## -prototype


````
PFND3DDDI_OFFERALLOCATIONSCB pfnOfferAllocationsCb;

__checkReturn HRESULT APIENTRY pfnOfferAllocationsCb(
  _In_       HANDLE                    hDevice,
  _In_ const D3DDDICB_OFFERALLOCATIONS *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a> structure at device creation.


### -param *








#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_offerallocations.md">D3DDDICB_OFFERALLOCATIONS</a> structure  that defines the video memory allocations that the driver offers.


## -returns




      Returns one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The  allocations were successfully offered.

<div class="alert"><b>Note</b>  If the driver does not need to call <a href="https://msdn.microsoft.com/library/windows/hardware/hh451693">pfnOfferAllocationsCb</a>, it should return <b>S_OK</b>.</div>
<div> </div>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl>
</td>
<td width="60%">

         The video memory manager or display miniport driver could not complete the operation because either a Plug and Play (PnP) Stop event or a Timeout Detection and Recovery (TDR) event occurred.

<div class="alert"><b>Note</b>  If this error code is returned, the driver's calling function (typically the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_offerresources.md">pfnOfferResources</a> routine) must return this error code to the  Direct3D runtime.</div>
<div> </div>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was supplied.

</td>
</tr>
</table>
 




## -remarks



The user-mode display driver calls <b>pfnOfferAllocationsCb</b> to notify the Microsoft DirectX graphics kernel subsystem that, after it completes any previously submitted render operations,  it can offer the allocations' memory for other processes to use.

After the driver calls <b>pfnOfferAllocationsCb</b> to offer an allocation to reuse, it must call <a href="https://msdn.microsoft.com/library/windows/hardware/hh451695">pfnReclaimAllocationsCb</a>  before it locks the allocation or submits it for rendering operations.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451695">pfnReclaimAllocationsCb</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_offerresources.md">pfnOfferResources</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_offerallocations.md">D3DDDICB_OFFERALLOCATIONS</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicecallbacks.md">D3DDDI_DEVICECALLBACKS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20pfnOfferAllocationsCb callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

