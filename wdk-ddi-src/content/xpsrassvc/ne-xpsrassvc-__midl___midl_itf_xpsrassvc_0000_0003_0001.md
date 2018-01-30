---
UID: NE:xpsrassvc.__MIDL___MIDL_itf_xpsrassvc_0000_0003_0001
title: "__MIDL___MIDL_itf_xpsrassvc_0000_0003_0001"
author: windows-driver-content
description: XPSRAS_PIXEL_FORMAT allows a caller to select the pixel format used by the IWICBitmap interface that is returned by the IXpsRasterizer::RasterizeRect method. XPSRAS_PIXEL_FORMAT is provided with Windows 8 and later versions of Windows.
old-location: print\xpsras_pixel_format.htm
old-project: print
ms.assetid: 54EA7ED6-BBE1-4110-8405-DEC0C5EA1C27
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: XPSRAS_PIXEL_FORMAT enumeration [Print Devices], xpsrassvc/XPSRAS_PIXEL_FORMAT_32BPP_PBGRA_UINT_SRGB, XPSRAS_PIXEL_FORMAT_64BPP_PRGBA_HALF_SCRGB, XPSRAS_PIXEL_FORMAT_32BPP_PBGRA_UINT_SRGB, print.xpsras_pixel_format, XPSRAS_PIXEL_FORMAT, XPSRAS_PIXEL_FORMAT_128BPP_PRGBA_FLOAT_SCRGB, __MIDL___MIDL_itf_xpsrassvc_0000_0003_0001, xpsrassvc/XPSRAS_PIXEL_FORMAT_64BPP_PRGBA_HALF_SCRGB, xpsrassvc/XPSRAS_PIXEL_FORMAT_128BPP_PRGBA_FLOAT_SCRGB, xpsrassvc/XPSRAS_PIXEL_FORMAT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: xpsrassvc.h
req.include-header: Xpsrassvc.h
req.target-type: Windows
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
-	HeaderDef
apilocation:
-	Xpsrassvc.h
apiname:
-	XPSRAS_PIXEL_FORMAT
product: Windows
targetos: Windows
req.typenames: XPSRAS_PIXEL_FORMAT
req.product: Windows 10 or later.
---

# __MIDL___MIDL_itf_xpsrassvc_0000_0003_0001 enumeration


## -description


<b>XPSRAS_PIXEL_FORMAT</b> allows a caller to select the pixel format used by the <a href="http://go.microsoft.com/fwlink/p/?linkid=133875">IWICBitmap</a> interface that is returned by the  <a href="https://msdn.microsoft.com/library/windows/hardware/ff556365">IXpsRasterizer::RasterizeRect</a> method. <b>XPSRAS_PIXEL_FORMAT</b> is provided with  Windows 8 and later versions of Windows.  


## -syntax


````
typedef enum _XPSRAS_PIXEL_FORMAT { 
  XPSRAS_PIXEL_FORMAT_32BPP_PBGRA_UINT_SRGB     = 1,
  XPSRAS_PIXEL_FORMAT_64BPP_PRGBA_HALF_SCRGB,
  XPSRAS_PIXEL_FORMAT_128BPP_PRGBA_FLOAT_SCRGB
} XPSRAS_PIXEL_FORMAT;
````


## -enum-fields




### -field XPSRAS_PIXEL_FORMAT_32BPP_PBGRA_UINT_SRGB

32-bit color pixel format. It is the default pixel format.


### -field XPSRAS_PIXEL_FORMAT_64BPP_PRGBA_HALF_SCRGB

64-bit color pixel format.


### -field XPSRAS_PIXEL_FORMAT_128BPP_PRGBA_FLOAT_SCRGB

128-bit color pixel format.


## -remarks


For more information about rasterizing XPS documents, see <a href="https://msdn.microsoft.com/a6a3746a-3638-464b-bca0-60003f37af76">Using the XPS Rasterization Service</a>.



## -see-also

<a href="http://msdn.microsoft.com/en-us/library/windows/desktop/ee719675.aspx">IWICBitmap</a>

<a href="https://msdn.microsoft.com/00F1C6B7-9AD8-4E42-B433-4BD73E85CFA3">IXpsRasterizationFactory1::CreateRasterizer1</a>

<a href="https://msdn.microsoft.com/a6a3746a-3638-464b-bca0-60003f37af76">Using the XPS Rasterization Service</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20XPSRAS_PIXEL_FORMAT enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

