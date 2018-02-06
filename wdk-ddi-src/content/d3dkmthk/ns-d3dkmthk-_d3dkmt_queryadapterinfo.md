---
UID: NS:d3dkmthk._D3DKMT_QUERYADAPTERINFO
title: "_D3DKMT_QUERYADAPTERINFO"
author: windows-driver-content
description: The D3DKMT_QUERYADAPTERINFO structure contains information that describes the graphics adapter.
old-location: display\d3dkmt_queryadapterinfo.htm
old-project: display
ms.assetid: 2bc9afc3-2fcf-4f62-85d4-67f824733904
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: KMTQUERYADAPTERINFOTYPE, _D3DKMT_QUERYADAPTERINFO, OpenGL_Structs_10a338e9-c5a8-44e0-9ad7-87d5a3ab742e.xml, D3DKMT_QUERYADAPTERINFO structure [Display Devices], d3dkmthk/D3DKMT_QUERYADAPTERINFO, D3DKMT_QUERYADAPTERINFO, display.d3dkmt_queryadapterinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Supported  starting with Windows Vista.
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
-	d3dkmthk.h
apiname:
-	D3DKMT_QUERYADAPTERINFO
product: Windows
targetos: Windows
req.typenames: D3DKMT_QUERYADAPTERINFO
---

# _D3DKMT_QUERYADAPTERINFO structure


## -description


The D3DKMT_QUERYADAPTERINFO structure contains information that describes the graphics adapter.


## -syntax


````
typedef struct _D3DKMT_QUERYADAPTERINFO {
  D3DKMT_HANDLE           hAdapter;
  KMTQUERYADAPTERINFOTYPE Type;
  VOID                    *pPrivateDriverData;
  UINT                    PrivateDriverDataSize;
} D3DKMT_QUERYADAPTERINFO;
````


## -struct-fields




### -field hAdapter

[in] A handle to the graphics adapter that information is retrieved about.


### -field Type

[in] A value of type KMTQUERYADAPTERINFOTYPE that indicates the type of information to retrieve. The following table lists the possible values.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KMTQAITYPE_UMDRIVERPRIVATE

</td>
<td>
The buffer that <b>pPrivateDriverData</b> points to is populated with private driver data in a vendor-specific format. To read and process the private data, a tight coupling between the OpenGL installable client driver (ICD) and the display miniport driver must exist.

</td>
</tr>
<tr>
<td>
KMTQAITYPE_UMDRIVERNAME

</td>
<td>
The <b>pPrivateDriverData</b> member points to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_umdfilenameinfo.md">D3DKMT_UMDFILENAMEINFO</a> structure that is filled with the name of the OpenGL ICD that depends on the particular version of DirectX. Non-DirectX applications can use this name to call the OpenGL ICD directly, although such usage is not recommended.

</td>
</tr>
<tr>
<td>
KMTQAITYPE_UMOPENGLINFO

</td>
<td>
<b>pPrivateDriverData</b> points to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_openglinfo.md">D3DKMT_OPENGLINFO</a> structure that contains information about the OpenGL ICD.

</td>
</tr>
<tr>
<td>
KMTQAITYPE_GETSEGMENTSIZE

</td>
<td>
<b>pPrivateDriverData</b> points to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_segmentsizeinfo.md">D3DKMT_SEGMENTSIZEINFO</a> structure that contains information about the size of memory and aperture segments.

</td>
</tr>
<tr>
<td>
KMTQAITYPE_ADAPTERGUID

</td>
<td>
<b>pPrivateDriverData</b> points to a variable that contains the GUID for the graphics adapter.

</td>
</tr>
<tr>
<td>
KMTQAITYPE_FLIPQUEUEINFO

</td>
<td>
<b>pPrivateDriverData</b> points to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_flipqueueinfo.md">D3DKMT_FLIPQUEUEINFO</a> structure that contains information about the queue of flip operations.

</td>
</tr>
<tr>
<td>
KMTQAITYPE_ADAPTERADDRESS

</td>
<td>
<b>pPrivateDriverData</b> points to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_adapteraddress.md">D3DKMT_ADAPTERADDRESS</a> structure that contains information about the physical location of the graphics adapter.

</td>
</tr>
<tr>
<td>
KMTQAITYPE_SETWORKINGSETINFO

</td>
<td>
<b>pPrivateDriverData</b> points to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_workingsetinfo.md">D3DKMT_WORKINGSETINFO</a> structure that contains information about the working set.

</td>
</tr>
<tr>
<td>
KMTQAITYPE_ADAPTERREGISTRYINFO

</td>
<td>
<b>pPrivateDriverData</b> points to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_adapterregistryinfo.md">D3DKMT_ADAPTERREGISTRYINFO</a> structure that contains registry information about the graphics adapter.

</td>
</tr>
<tr>
<td>
KMTQAITYPE_CURRENTDISPLAYMODE

</td>
<td>
<b>pPrivateDriverData</b> points to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_currentdisplaymode.md">D3DKMT_CURRENTDISPLAYMODE</a> structure that contains the current display mode.

</td>
</tr>
<tr>
<td>
KMTQAITYPE_MODELIST

</td>
<td>
<b>pPrivateDriverData</b> points to an array of <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_displaymode.md">D3DKMT_DISPLAYMODE</a> structures for the list of display modes.

</td>
</tr>
<tr>
<td>
KMTQAITYPE_CHECKDRIVERUPDATESTATUS

</td>
<td>
<b>pPrivateDriverData</b> points to the driver update status.

</td>
</tr>
<tr>
<td>
KMTQAITYPE_VIRTUALADDRESSINFO 

</td>
<td>
Reserved for future use.

Supported starting with  Windows 7.

</td>
</tr>
<tr>
<td>
KMTQAITYPE_DRIVERVERSION

</td>
<td>
<b>pPrivateDriverData</b> points to a variable that contains a <a href="..\d3dkmthk\ne-d3dkmthk-_qai_driverversion.md">D3DKMT_DRIVERVERSION</a>-typed value that indicates the version of the display driver model that the display miniport driver supports.

Supported starting with  Windows 7.

</td>
</tr>
<tr>
<td>
KMTQAITYPE_ADAPTERTYPE

</td>
<td>
<b>pPrivateDriverData</b> points to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_adaptertype.md">D3DKMT_ADAPTERTYPE</a> structure that specifies the  graphics adapter type.

Supported starting with  Windows 8.

</td>
</tr>
<tr>
<td>
KMTQAITYPE_OUTPUTDUPLCONTEXTSCOUNT

</td>
<td>
<b>pPrivateDriverData</b> points to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_outputduplcontextscount.md">D3DKMT_OUTPUTDUPLCONTEXTSCOUNT</a> structure that specifies the  number of current <a href="https://msdn.microsoft.com/523FBFAD-5D78-4EE3-A3B7-8FD5BA39DC46">Desktop Duplication API</a> (DDA) clients that are attached to a given video present network (VidPN).

Supported starting with  Windows 8.

</td>
</tr>
<tr>
<td>
KMTQAITYPE_WDDM_1_2_CAPS

</td>
<td>
<b>pPrivateDriverData</b> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406678">D3DKMT_WDDM_1_2_CAPS</a> structure that specifies the  WDDM 1.2 and later capabilities of the graphics adapter and display miniport driver.

Supported starting with  Windows 8.

</td>
</tr>
<tr>
<td>
KMTQAITYPE_UMD_DRIVER_VERSION

</td>
<td>
<b>pPrivateDriverData</b> points to a  <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_umd_driver_version.md">D3DKMT_UMD_DRIVER_VERSION</a> structure that specifies the  user-mode driver version.

Supported starting with  Windows 8.

</td>
</tr>
<tr>
<td>
KMTQAITYPE_DIRECTFLIP_SUPPORT

</td>
<td>
<b>pPrivateDriverData</b> points to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_directflip_support.md">D3DKMT_DIRECTFLIP_SUPPORT</a> structure that specifies whether the user-mode driver supports Direct Flip operations.

Supported starting with  Windows 8.

</td>
</tr>
<tr>
<td>
KMTQAITYPE_MULTIPLANEOVERLAY_SUPPORT

</td>
<td>
Reserved for future use.

Supported starting with  Windows 8.1.

</td>
</tr>
<tr>
<td>
KMTQAITYPE_DLIST_DRIVER_NAME

</td>
<td>
Reserved for future use.

Supported starting with  Windows 8.1.

</td>
</tr>
<tr>
<td>
KMTQAITYPE_WDDM_1_3_CAPS

</td>
<td>
Reserved for future use.

Supported starting with  Windows 8.1.

</td>
</tr>
</table> 


### -field pPrivateDriverData

[out] A pointer to a buffer that the display miniport driver can fill with the requested information.


### -field PrivateDriverDataSize

[in/out] The size, in bytes, of the buffer that <b>pPrivateDriverData</b> points to.


## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_workingsetinfo.md">D3DKMT_WORKINGSETINFO</a>

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_adaptertype.md">D3DKMT_ADAPTERTYPE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406678">D3DKMT_WDDM_1_2_CAPS</a>

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_umd_driver_version.md">D3DKMT_UMD_DRIVER_VERSION</a>

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_directflip_support.md">D3DKMT_DIRECTFLIP_SUPPORT</a>

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_adapterregistryinfo.md">D3DKMT_ADAPTERREGISTRYINFO</a>

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_openglinfo.md">D3DKMT_OPENGLINFO</a>

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_flipqueueinfo.md">D3DKMT_FLIPQUEUEINFO</a>

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_displaymode.md">D3DKMT_DISPLAYMODE</a>

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_adapteraddress.md">D3DKMT_ADAPTERADDRESS</a>

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_currentdisplaymode.md">D3DKMT_CURRENTDISPLAYMODE</a>

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryadapterinfo.md">D3DKMTQueryAdapterInfo</a>

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_segmentsizeinfo.md">D3DKMT_SEGMENTSIZEINFO</a>

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_umdfilenameinfo.md">D3DKMT_UMDFILENAMEINFO</a>

<a href="..\d3dkmthk\ne-d3dkmthk-_qai_driverversion.md">D3DKMT_DRIVERVERSION</a>

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_outputduplcontextscount.md">D3DKMT_OUTPUTDUPLCONTEXTSCOUNT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_QUERYADAPTERINFO structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

