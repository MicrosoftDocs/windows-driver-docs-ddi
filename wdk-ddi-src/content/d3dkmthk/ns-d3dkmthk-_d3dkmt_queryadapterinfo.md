---
UID: NS:d3dkmthk._D3DKMT_QUERYADAPTERINFO
title: "_D3DKMT_QUERYADAPTERINFO"
author: windows-driver-content
description: The D3DKMT_QUERYADAPTERINFO structure contains information that describes the graphics adapter.
old-location: display\d3dkmt_queryadapterinfo.htm
ms.assetid: 2bc9afc3-2fcf-4f62-85d4-67f824733904
ms.date: 05/10/2018
ms.keywords: D3DKMT_QUERYADAPTERINFO, D3DKMT_QUERYADAPTERINFO structure [Display Devices], OpenGL_Structs_10a338e9-c5a8-44e0-9ad7-87d5a3ab742e.xml, _D3DKMT_QUERYADAPTERINFO, d3dkmthk/D3DKMT_QUERYADAPTERINFO, display.d3dkmt_queryadapterinfo
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_QUERYADAPTERINFO
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_QUERYADAPTERINFO
---

# _D3DKMT_QUERYADAPTERINFO structure


## -description


The D3DKMT_QUERYADAPTERINFO structure contains information that describes the graphics adapter.


## -struct-fields




### -field hAdapter

[in] A handle to the graphics adapter that information is retrieved about.


### -field Type

[in] A value of type KMTQUERYADAPTERINFOTYPE that indicates the type of information to retrieve. The following table lists the possible values.

| **Value** | **Meaning** | 
|:--|:--|
| KMTQAITYPE_UMDRIVERPRIVATE | The buffer that pPrivateDriverDatapoints to is populated with private driver data in a vendor-specific format. To read and process the private data, a tight coupling between the OpenGL installable client driver (ICD) and the display miniport driver must exist. | 
| KMTQAITYPE_UMDRIVERNAME | The pPrivateDriverData member points to a [D3DKMT_UMDFILENAMEINFO](https://msdn.microsoft.com/library/windows/hardware/ff548384) structure that is filled with the name of the OpenGL ICD that depends on the particular version of DirectX. Non-DirectX applications can use this name to call the OpenGL ICD directly, although such usage is not recommended. | 
| KMTQAITYPE_UMOPENGLINFO | pPrivateDriverData points to a [D3DKMT_OPENGLINFO](https://msdn.microsoft.com/library/windows/hardware/ff548123)  structure that contains information about the OpenGL ICD. | 
| KMTQAITYPE_GETSEGMENTSIZE | pPrivateDriverData points to a [D3DKMT_SEGMENTSIZEINFO](https://msdn.microsoft.com/library/windows/hardware/ff548256)  structure that contains information about the size of memory and aperture segments. | 
| KMTQAITYPE_ADAPTERGUID | pPrivateDriverData points to a variable that contains the GUID for the graphics adapter. | 
| KMTQAITYPE_FLIPQUEUEINFO | pPrivateDriverData points to a [D3DKMT_FLIPQUEUEINFO](https://msdn.microsoft.com/library/windows/hardware/ff548010)  structure that contains information about the queue of flip operations. | 
| KMTQAITYPE_ADAPTERADDRESS | pPrivateDriverData points to a [D3DKMT_ADAPTERADDRESS](https://msdn.microsoft.com/library/windows/hardware/ff547280)  structure that contains information about the physical location of the graphics adapter. | 
| KMTQAITYPE_SETWORKINGSETINFO | pPrivateDriverData points to a [D3DKMT_WORKINGSETINFO](https://msdn.microsoft.com/library/windows/hardware/ff548457)  structure that contains information about the working set. | 
| KMTQAITYPE_ADAPTERREGISTRYINFO | pPrivateDriverData points to a [D3DKMT_ADAPTERREGISTRYINFO](https://msdn.microsoft.com/library/windows/hardware/ff547286) structure that contains registry information about the graphics adapter. | 
| KMTQAITYPE_CURRENTDISPLAYMODE | pPrivateDriverData points to a [D3DKMT_CURRENTDISPLAYMODE](https://msdn.microsoft.com/library/windows/hardware/ff547860) structure that contains the current display mode. | 
| KMTQAITYPE_MODELIST | pPrivateDriverData points to an array of [D3DKMT_DISPLAYMODE](https://msdn.microsoft.com/library/windows/hardware/ff547942)  structures for the list of display modes. | 
| KMTQAITYPE_CHECKDRIVERUPDATESTATUS | pPrivateDriverData points to the driver update status. | 
| KMTQAITYPE_VIRTUALADDRESSINFO | Reserved for future use. Supported starting with Windows 7. | 
| KMTQAITYPE_DRIVERVERSION | pPrivateDriverData points to a variable that contains a [D3DKMT_DRIVERVERSION](https://msdn.microsoft.com/library/windows/hardware/ff547964) -typed value that indicates the version of the display driver model that the display miniport driver supports. Supported starting with Windows 7. | 
| KMTQAITYPE_ADAPTERTYPE | pPrivateDriverData points to a [D3DKMT_ADAPTERTYPE](https://msdn.microsoft.com/library/windows/hardware/hh439472)  structure that specifies the graphics adapter type. Supported starting with Windows 8. | 
| KMTQAITYPE_OUTPUTDUPLCONTEXTSCOUNT | pPrivateDriverData points to a [D3DKMT_OUTPUTDUPLCONTEXTSCOUNT](https://msdn.microsoft.com/library/windows/hardware/hh406505) structure that specifies the number of current [Desktop Duplication API](https://msdn.microsoft.com/523FBFAD-5D78-4EE3-A3B7-8FD5BA39DC46)  (DDA) clients that are attached to a given video present network (VidPN). Supported starting with Windows 8. | 
| KMTQAITYPE_WDDM_1_2_CAPS | pPrivateDriverData points to a [D3DKMT_WDDM_1_2_CAPS](https://msdn.microsoft.com/library/windows/hardware/hh406678)  structure that specifies the WDDM 1.2 and later capabilities of the graphics adapter and display miniport driver. Supported starting with Windows 8. | 
| KMTQAITYPE_UMD_DRIVER_VERSION | pPrivateDriverData points to a[D3DKMT_UMD_DRIVER_VERSION](https://msdn.microsoft.com/library/windows/hardware/hh406598) structure that specifies the user-mode driver version. Supported starting with Windows 8. | 
| KMTQAITYPE_DIRECTFLIP_SUPPORT | pPrivateDriverData points to a [D3DKMT_DIRECTFLIP_SUPPORT](https://msdn.microsoft.com/library/windows/hardware/hh406459)  structure that specifies whether the user-mode driver supports Direct Flip operations. Supported starting with Windows 8. | 
| KMTQAITYPE_MULTIPLANEOVERLAY_SUPPORT | Reserved for future use. Supported starting with Windows 8.1. | 
| KMTQAITYPE_DLIST_DRIVER_NAME | Reserved for future use. Supported starting with Windows 8.1. | 
| KMTQAITYPE_WDDM_1_3_CAPS | Reserved for future use. Supported starting with Windows 8.1. | 




### -field pPrivateDriverData

[out] A pointer to a buffer that the display miniport driver can fill with the requested information.


### -field PrivateDriverDataSize

[in/out] The size, in bytes, of the buffer that <b>pPrivateDriverData</b> points to.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547100">D3DKMTQueryAdapterInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547280">D3DKMT_ADAPTERADDRESS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547286">D3DKMT_ADAPTERREGISTRYINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439472">D3DKMT_ADAPTERTYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547860">D3DKMT_CURRENTDISPLAYMODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406459">D3DKMT_DIRECTFLIP_SUPPORT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547942">D3DKMT_DISPLAYMODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547964">D3DKMT_DRIVERVERSION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548010">D3DKMT_FLIPQUEUEINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548123">D3DKMT_OPENGLINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406505">D3DKMT_OUTPUTDUPLCONTEXTSCOUNT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548256">D3DKMT_SEGMENTSIZEINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548384">D3DKMT_UMDFILENAMEINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406598">D3DKMT_UMD_DRIVER_VERSION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406678">D3DKMT_WDDM_1_2_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548457">D3DKMT_WORKINGSETINFO</a>
 

 

