---
UID: NC:d3dumddi.PFND3DDDI_OFFERRESOURCES
title: PFND3DDDI_OFFERRESOURCES
author: windows-driver-content
description: Called by the Microsoft Direct3D runtime to request that the user-mode display driver offer video memory resources for reuse.
old-location: display\offerresources.htm
old-project: display
ms.assetid: 68551AD7-AC0C-4138-948F-33773F02DA41
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: OfferResources, OfferResources callback function [Display Devices], PFND3DDDI_OFFERRESOURCES, d3dumddi/OfferResources, display.offerresources
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	OfferResources
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_OFFERRESOURCES callback


## -description


Called by the Microsoft Direct3D runtime to request that the user-mode display driver  offer video memory resources for reuse.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh451078">D3DDDIARG_OFFERRESOURCES</a> structure that defines the video memory resources that the driver offers.


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
The video memory resources were successfully offered.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl>
</td>
<td width="60%">

         The driver detected that the display adapter was removed, so the driver did not complete the operation.

If the driver is not aware of the adapter removal, the driver is not required to return this error code.

</td>
</tr>
</table>
 




## -remarks



If the user-mode driver does not have outstanding work queued that references an allocation that it has been asked to offer, then it can offer the allocation immediately or postpone the offer until the next call is made to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh463886">Flush</a> or <a href="https://msdn.microsoft.com/e90683b4-64b6-4018-96a5-b50118df3367">Present</a> functions. However, the driver must always process all batched offer calls that have been submitted through <i>Flush</i> or <i>Present</i>.

If the driver uses the <a href="https://msdn.microsoft.com/f22e19ba-9ff3-4aa1-a3f0-103f67ea7c60">renaming service</a> of the video memory manager, then the driver should offer the last allocation instance.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451078">D3DDDIARG_OFFERRESOURCES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh463886">Flush</a>



<a href="https://msdn.microsoft.com/e90683b4-64b6-4018-96a5-b50118df3367">Present</a>



<a href="https://msdn.microsoft.com/F0533DBB-CB18-4556-9871-2DF4CA719172">ReclaimResources</a>
 

 

