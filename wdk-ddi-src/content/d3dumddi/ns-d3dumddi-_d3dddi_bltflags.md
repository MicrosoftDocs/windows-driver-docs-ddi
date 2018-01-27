---
UID: NS:d3dumddi._D3DDDI_BLTFLAGS
title: _D3DDDI_BLTFLAGS
author: windows-driver-content
description: The D3DDDI_BLTFLAGS structure identifies the type of bit-block transfer (bitblt) to perform.
old-location: display\d3dddi_bltflags.htm
old-project: display
ms.assetid: 844d6aed-2ca2-45ef-bd53-54344dbdadbf
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDI_BLTFLAGS structure [Display Devices], display.d3dddi_bltflags, D3DDDI_BLTFLAGS, d3dumddi/D3DDDI_BLTFLAGS, D3D_other_Structs_8d70fa64-3813-4165-a64d-4e91287e05d5.xml, _D3DDDI_BLTFLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
-	D3DDDI_BLTFLAGS
product: Windows
targetos: Windows
req.typenames: D3DDDI_BLTFLAGS
---

# _D3DDDI_BLTFLAGS structure


## -description


The D3DDDI_BLTFLAGS structure identifies the type of bit-block transfer (bitblt) to perform.


## -syntax


````
typedef struct _D3DDDI_BLTFLAGS {
  union {
    struct {
      UINT Point  :1;
      UINT Linear  :1;
      UINT SrcColorKey  :1;
      UINT DstColorKey  :1;
      UINT MirrorLeftRight  :1;
      UINT MirrorUpDown  :1;
      UINT LinearToSrgb  :1;
      UINT Rotate  :1;
      UINT BeginPresentToDwm  :1;
      UINT ContinuePresentToDwm  :1;
      UINT EndPresentToDwm  :1;
#if (D3D_UMD_INTERFACE_VERSION < D3D_UMD_INTERFACE_VERSION_WIN8)
      UINT Reserved  :21;
#else 
      UINT Discard  :1;
      UINT NoOverwrite  :1;
      UINT Tileable  :1;
      UINT Reserved  :18;
#endif 
    };
    UINT Value;
  };
} D3DDDI_BLTFLAGS;
````


## -struct-fields




### -field Point

A UINT value that specifies whether to use point filtering in the bit-block transfer. Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Linear

A UINT value that specifies whether to use linear filtering in the bit-block transfer. Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field SrcColorKey

A UINT value that specifies whether to perform source color-keying by using the value in the <b>ColorKey</b> member. That is, any pixel in the source surface that matches the color key should not be copied to the destination surface, and all of the source pixels that do not match the color key should be copied. 

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field DstColorKey

A UINT value that specifies whether to perform destination color-keying by using the value in the <b>ColorKey</b> member. That is, any pixel in the destination surface that matches the color key should be replaced with the corresponding pixel from the source surface, and all of the destination pixels that do not match the color key should not be replaced.

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field MirrorLeftRight

A UINT value that specifies whether the contents of the source surface are flipped horizontally along the center axis in the bitblt to the destination surface. That is, contents on the left side of the source surface are copied to the right side of the destination surface, and vice versa.

Setting this member is equivalent to setting the fifth bit of the 32-bit <b>Value</b> member (0x00000010).


### -field MirrorUpDown

A UINT value that specifies whether the contents of the source surface are flipped vertically along the center axis in the bitblt to the destination surface. That is, the contents on the top of the source surface are copied to the bottom of the destination surface, and vice versa.

Setting this member is equivalent to setting the sixth bit of the 32-bit <b>Value</b> member (0x00000020).


### -field LinearToSrgb

A UINT value that specifies whether to convert the linear-formatted source to sRGB format during the bitblt operation. sRGB format is gamma corrected. For more information about sRGB format, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=10112">sRGB</a> website.

Setting this member is equivalent to setting the seventh bit of the 32-bit <b>Value</b> member (0x00000040).


### -field Rotate

A UINT value that specifies whether to rotate the source during the bitblt operation. 

Setting this member is equivalent to setting the eighth bit of the 32-bit <b>Value</b> member (0x00000080).


### -field BeginPresentToDwm

A UINT value that specifies whether the Microsoft Direct3D runtime begins a DWM present operation during the bitblt operation. For more information about <b>BeginPresentToDwm</b>, see Remarks.

Setting this member is equivalent to setting the ninth bit of the 32-bit <b>Value</b> member (0x00000100).


### -field ContinuePresentToDwm

A UINT value that specifies whether the Direct3D runtime continues a DWM present operation during the bitblt operation. For more information about <b>ContinuePresentToDwm</b>, see Remarks.

Setting this member is equivalent to setting the tenth bit of the 32-bit <b>Value</b> member (0x00000200).


### -field EndPresentToDwm

A UINT value that specifies whether the Direct3D runtime ends a DWM present operation during the bitblt operation. For more information about <b>EndPresentToDwm</b>, see Remarks.

Setting this member is equivalent to setting the eleventh bit of the 32-bit <b>Value</b> member (0x00000400).


### -field Discard

Indicates that the user-mode display driver can discard previous contents of the entire resource. The driver can take advantage of this capability to optimize performance and memory usage.

If this member is not <b>NULL</b>, <b>NoOverwrite</b> and  <b>Tileable</b> must be <b>NULL</b>.

Setting this member is equivalent to setting the twelfth bit (0xFFFFF800) of the 32-bit <b>Value</b> member to zeros.

Supported starting with Windows 8.


### -field NoOverwrite

Indicates that the caller guarantees that the portion of the surface that is being written to with new data is not currently being referenced or accessed by any previous render operation. The driver can take advantage of this capability to optimize performance and memory usage.

If this member is not <b>NULL</b>, <b>Discard</b> must be <b>NULL</b>.

Setting this member is equivalent to setting the thirteenth bit (0x00001000) of the 32-bit <b>Value</b> member to zeros.

Supported starting with Windows 8.


### -field Tileable

For tile-based deferred rendering, indicates that a copy operation can operate on only the currently processed tile in the source or destination resource, and the scene does not have to be flushed in all tiles.

If this member is not <b>NULL</b>, <b>Discard</b> must be <b>NULL</b>.

Setting this member is equivalent to setting the fourteenth bit (0x00002000) of the 32-bit <b>Value</b> member to zeros.

Supported starting with Windows 8.


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 21 bits (0xFFFFF800) of the 32-bit <b>Value</b> member to zeros.

This member is reserved and should be set to zero. 

Setting this member to zero is equivalent to setting the remaining 18 bits (0xFFFFC000) of the 32-bit <b>Value</b> member to zeros.

Supported starting with Windows 8.


### -field Value

A member in the union that is contained in D3DDDI_BLTFLAGS that can hold one 32-bit value that identifies the type of bitblt to perform.


## -remarks


The <b>BeginPresentToDwm</b>, <b>ContinuePresentToDwm</b>, and <b>EndPresentToDwm</b> bit-field flags inform the user-mode display driver about the time when the Direct3D runtime performs parts of a DWM present operation.  Because DWM present operations can occur in multiple steps, the Direct3D runtime uses these flags to mark the steps in a sequence of bitblts. For example:  
<ul>
<li>If the present operation consists of one bitblt, the bitblt is marked as follows:<ul>
<li><b>BeginPresentToDwm</b> = <b>TRUE</b>;</li>
<li><b>ContinuePresentToDwm</b> = <b>FALSE</b>;</li>
<li><b>EndPresentToDwm</b> = <b>TRUE</b>;</li>
</ul>
</li>
<li>If the present operation consists of two bitblts, the bitblts are marked as shown in two sequential bitblt operations:<ol>
<li>First bitblt:<ul>
<li><b>BeginPresentToDwm</b> = <b>TRUE</b>;</li>
<li><b>ContinuePresentToDwm</b> = <b>FALSE</b>;</li>
<li><b>EndPresentToDwm</b> = <b>FALSE</b>;</li>
</ul>
</li>
<li>Second bitblt:<ul>
<li><b>BeginPresentToDwm</b> = <b>FALSE</b>;</li>
<li><b>ContinuePresentToDwm</b> = <b>FALSE</b>;</li>
<li><b>EndPresentToDwm</b> = <b>TRUE</b>;</li>
</ul>
</li>
</ol>
</li>
<li>If the present operation consists of three or more bitblts, the bitblts are marked as shown in the following sequential bitblt operations:<ol>
<li>First bitblt:<ul>
<li><b>BeginPresentToDwm</b> = <b>TRUE</b>;</li>
<li><b>ContinuePresentToDwm</b> = <b>FALSE</b>;</li>
<li><b>EndPresentToDwm</b> = <b>FALSE</b>;</li>
</ul>
</li>
<li>Second and successive bitblts, not including the final bitblt:<ul>
<li><b>BeginPresentToDwm</b> = <b>FALSE</b>;</li>
<li><b>ContinuePresentToDwm</b> = <b>TRUE</b>;</li>
<li><b>EndPresentToDwm</b> = <b>FALSE</b>;</li>
</ul>
</li>
<li>Final bitblt:<ul>
<li><b>BeginPresentToDwm</b> = <b>FALSE</b>;</li>
<li><b>ContinuePresentToDwm</b> = <b>FALSE</b>;</li>
<li><b>EndPresentToDwm</b> = <b>TRUE</b>;</li>
</ul>
</li>
</ol>
</li>
</ul>


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_blt.md">D3DDDIARG_BLT</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_flush.md">Flush</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_BLTFLAGS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

