---
UID: NC:d3d10umddi.PFND3D10DDI_SETTEXTFILTERSIZE
title: PFND3D10DDI_SETTEXTFILTERSIZE
author: windows-driver-content
description: The SetTextFilterSize function sets the width and height of the monochrome convolution filter.
old-location: display\settextfiltersize.htm
old-project: display
ms.assetid: 663fd3c3-7a8f-446d-b45a-392716116407
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.settextfiltersize, SetTextFilterSize callback function [Display Devices], SetTextFilterSize, PFND3D10DDI_SETTEXTFILTERSIZE, PFND3D10DDI_SETTEXTFILTERSIZE, d3d10umddi/SetTextFilterSize, UserModeDisplayDriverDx10_Functions_418992fe-bd22-446c-94a2-2a4d23fd63a7.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
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
-	UserDefined
apilocation:
-	d3d10umddi.h
apiname:
-	SetTextFilterSize
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D10DDI_SETTEXTFILTERSIZE callback


## -description


The <i>SetTextFilterSize</i> function sets the width and height of the monochrome convolution filter.


## -prototype


````
PFND3D10DDI_SETTEXTFILTERSIZE SetTextFilterSize;

VOID APIENTRY SetTextFilterSize(
  _In_ D3D10DDI_HDEVICE hDevice,
  _In_ UINT             Width,
  _In_ UINT             Height
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param UINT








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - Width [in]

 The width of the monochrome convolution filter. The width can be from 1 to 7 texels.


#### - Height [in]

 The height of the monochrome convolution filter. The height can be from 1 to 7 texels.


## -returns



None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The number of samples that are required from a kernel's dimensions is actually (<i>Width</i> + 1) x (<i>Height</i> + 1), which can come out to from 4 to 64 samples. These settings apply across all samplers that are configured to use the D3D10_DDI_FILTER_TEXT_1BIT filter from the <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_filter.md">D3D10_DDI_FILTER</a> enumeration.

<i>SetTextFilterSize</i> ensures that values that are supplied in the <i>Width</i> and <i>Height</i> parameters are in range. The default vaules for <i>Width</i> and <i>Height</i> are both 1, initially. The driver must set these default values during device creation.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED. However, if device removal interfered with the operation of <i>SetTextFilterSize</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_filter.md">D3D10_DDI_FILTER</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_SETTEXTFILTERSIZE callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

