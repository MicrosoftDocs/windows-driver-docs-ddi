---
UID: NS:d3dhal._DD_GETDRIVERINFO2DATA
title: _DD_GETDRIVERINFO2DATA (d3dhal.h)
description: DirectX 8.0 and later versions only. DD_GETDRIVERINFO2DATA is passed in the lpvData member of the DD_GETDRIVERINFODATA structure when GUID_GetDriverInfo2 is specified in the guidInfo member of DD_GETDRIVERINFODATA in a DdGetDriverInfo call.
old-location: display\dd_getdriverinfo2data.htm
tech.root: display
ms.assetid: f1b3e432-6972-49ff-9fce-b642c1be17ea
ms.date: 05/10/2018
ms.keywords: DD_GETDRIVERINFO2DATA, DD_GETDRIVERINFO2DATA structure [Display Devices], _DD_GETDRIVERINFO2DATA, d3dhal/DD_GETDRIVERINFO2DATA, d3dstrct_64ab01fc-414f-4367-8bb7-201c7e120275.xml, display.dd_getdriverinfo2data
ms.topic: struct
f1_keywords:
 - "d3dhal/DD_GETDRIVERINFO2DATA"
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dhal.h
api_name:
- DD_GETDRIVERINFO2DATA
product:
- Windows
targetos: Windows
req.typenames: DD_GETDRIVERINFO2DATA
---

# _DD_GETDRIVERINFO2DATA structure


## -description



   DirectX 8.0 and later versions only.
   

DD_GETDRIVERINFO2DATA is passed in the <b>lpvData</b> member of the <a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/ns-ddrawint-_dd_getdriverinfodata">DD_GETDRIVERINFODATA</a> structure when GUID_GetDriverInfo2 is specified in the <b>guidInfo</b> member of DD_GETDRIVERINFODATA in a <a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/nc-ddrawint-pdd_getdriverinfo">DdGetDriverInfo</a> call.


## -struct-fields




### -field dwReserved

Specifies a reserved field. Driver should not read or write.


### -field dwMagic

Specifies the magic number. Has the value D3DGDI2_MAGIC if this is a <a href="https://docs.microsoft.com/windows-hardware/drivers/display/supporting-getdriverinfo2">GetDriverInfo2</a> call. Otherwise this structure is, in fact, a <a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/ns-ddrawint-_dd_stereomode">DD_STEREOMODE</a> call.


### -field dwType

Specifies the type of information requested, which can contain one of the following D3DGDI2_TYPE_<i>Xxx</i> values. Driver should only read (not write) this member.
	

| **Value** | **Meaning** | 
|:--|:--|
| D3DGDI2_TYPE_DEFER_AGP_FREES | **NT-based operating systems only.**<br/>Is used to notify the driver that it should properly handle the destruction of [AGP memory](https://docs.microsoft.com/windows-hardware/drivers/display/agp-support)  for surfaces. The runtime provides a pointer to a [DD_FREE_DEFERRED_AGP_DATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_free_deferred_agp_data) structure in the lpvData field of the DD_GETDRIVERINFODATA data structure.<br/>The driver sometimes receives this notification before a display mode change occurs. The runtime only sends this notification if it is to be used to perform the display mode change. Drivers should check the process identifier (PID) of the process destroying the surface against the process that created the surface. If the PIDs are different, the driver probably should not destroy the user-mode mappings of the AGP memory because an application might still be using the memory. | 
| D3DGDI2_TYPE_DEFERRED_AGP_AWARE | **NT-based operating systems only.**<br/>Is used to inform the driver that the runtime sends D3DGDI2_TYPE_FREE_DEFERRED_AGP and D3DGDI2_TYPE_DEFER_AGP_FREES notifications at the appropriate time (such as, after the last outstanding [AGP memory](https://docs.microsoft.com/windows-hardware/drivers/display/agp-support)  lock is released). The runtime provides a pointer to a [DD_DEFERRED_AGP_AWARE_DATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_deferred_agp_aware_data) structure in the lpvData field of the DD_GETDRIVERINFODATA data structure. | 
| D3DGDI2_TYPE_DXVERSION | Is used to notify the driver of the current DX runtime version being used by the application. The runtime provides a pointer to a [DD_DXVERSION](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_dxversion) structure in the lpvData field of the DD_GETDRIVERINFODATA data structure. | 
| D3DGDI2_TYPE_FREE_DEFERRED_AGP | **NT-based operating systems only.**<br/>Is used to notify the driver that it is now safe to destroy all the user-mode mappings of the [AGP memory](https://docs.microsoft.com/windows-hardware/drivers/display/agp-support) . The driver preserved these user-mode mappings when surfaces were destroyed and it received a D3DGDI2_TYPE_DEFER_AGP_FREES notification. The runtime provides a pointer to a [DD_FREE_DEFERRED_AGP_DATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_free_deferred_agp_data) structure in the lpvData field of the DD_GETDRIVERINFODATA data structure.<br/>The driver receives this notification when all display devices within the process stop using surfaces, textures, vertex buffers, and index buffers that were locked at the time of the display mode change. | 
| D3DGDI2_TYPE_GETADAPTERGROUP | **DirectX 9.0 and later versions only.**<br/>Is used to query the driver for the identity of the group of adapters that are part of its multiple-head video card. This group shares video hardware like video memory and the 3D accelerator. The driver should set the data structure pointed to by the lpvData field of the DD_GETDRIVERINFODATA data structure to [DD_GETADAPTERGROUPDATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_getadaptergroupdata). | 
| D3DGDI2_TYPE_GETD3DCAPS8 | This type indicates that the runtime requests to receive a D3DCAPS8 structure giving the DirectX 8.0 style capabilities of the device. The driver should copy an initialized D3DCAPS8 structure into the lpvData field of the DD_GETDRIVERINFODATA structure. | 
| D3DGDI2_TYPE_GETD3DCAPS9 | **Required for DirectX 9.0 and later versions only.**<br/>This type indicates that the runtime requests to receive a D3DCAPS9 structure giving the DirectX 9.0 style capabilities of the device. The driver should copy an initialized D3DCAPS9 structure into the lpvData field of the DD_GETDRIVERINFODATA structure. | 
| D3DGDI2_TYPE_GETD3DQUERY | **DirectX 9.0 and later versions only.** <br/>Is used to query the driver for information about a particular query type that it supports. The driver should set the data structure pointed to by thelpvData field of the DD_GETDRIVERINFODATA data structure to [DD_GETD3DQUERYDATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_getd3dquerydata). | 
| D3DGDI2_TYPE_GETD3DQUERYCOUNT | **DirectX 9.0 and later versions only.**<br/>Is used to query the driver for the number of query types that it supports. The driver should set the data structure pointed to by the lpvData field of the DD_GETDRIVERINFODATA data structure to [DD_GETD3DQUERYCOUNTDATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_getd3dquerycountdata). | 
| D3DGDI2_TYPE_GETDDIVERSION | **DirectX 9.0 and later versions only.**<br/>Is used to query the driver for the version of the DDI that the driver supports; this DDI version, in turn, depends on the version of DirectX that makes this request. The driver should set the dwDDIVersion member of the [DD_GETDDIVERSIONDATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_getddiversiondata) structure, which the lpvData field of the DD_GETDRIVERINFODATA data structure points to, to the appropriate DDI version. | 
| D3DGDI2_TYPE_GETEXTENDEDMODE | **DirectX 9.0 and later versions only.**<br/>Is used to query the driver for information about a particular extended display mode that it supports. The driver should set the data structure pointed to by the lpvData field of the DD_GETDRIVERINFODATA data structure to [DD_GETEXTENDEDMODEDATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_getextendedmodedata). | 
| D3DGDI2_TYPE_GETEXTENDEDMODECOUNT | **DirectX 9.0 and later versions only.**<br/>Is used to query the driver for the number of extended display modes that it supports. The driver should set the data structure pointed to by the lpvData field of the DD_GETDRIVERINFODATA data structure to [DD_GETEXTENDEDMODECOUNTDATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_getextendedmodecountdata). | 
| D3DGDI2_TYPE_GETFORMAT | Is used to query for a particular surface format from the driver. The data structure pointed to by the lpvDatafield of the DD_GETDRIVERINFODATA data structure is [DD_GETFORMATDATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_getformatdata) . | 
| D3DGDI2_TYPE_GETFORMATCOUNT | Is used to request the number of DirectX 8.0 and later style surface formats supported by the driver. The data structure pointed to by thelpvData field of the DD_GETDRIVERINFODATA is [DD_GETFORMATCOUNTDATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_getformatcountdata). | 
| D3DGDI2_TYPE_GETMULTISAMPLEQUALITYLEVELS | **DirectX 9.0 and later versions only.**<br/>Is used to query the driver for the number of multiple-sample quality levels for a given render-target format that it supports. Whether the display device supports maskable or submaskable multisampling, the driver for the device must provide the number of quality levels for the D3DMULTISAMPLE_NONMASKABLE multiple-sample type. The driver should set the data structure pointed to by the lpvData field of the DD_GETDRIVERINFODATA data structure to [DD_MULTISAMPLEQUALITYLEVELSDATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_multisamplequalitylevelsdata). |

 


### -field dwExpectedSize

Specifies the expected size, in bytes, of the information requested. Driver should only read (not write) this member.


## -remarks



The <b>dwExpectedSize</b> member of the DD_GETDRIVERINFODATA structure is not used when a <a href="https://docs.microsoft.com/windows-hardware/drivers/display/supporting-getdriverinfo2">GetDriverInfo2</a> request is being made. Its value is undefined in this case and should be ignored. Instead, the actual expected size of the data is found in the <b>dwExpectedSize</b> member of DD_GETDRIVERINFO2DATA.

The following code fragment demonstrates how to handle <a href="https://docs.microsoft.com/windows-hardware/drivers/display/supporting-getdriverinfo2">GetDriverInfo2</a>:

```cpp
D3DCAPS8 myD3DCaps8 = { ... };

DWORD CALLBACK
DdGetDriverInfo(LPDDHAL_GETDRIVERINFODATA lpData)
{
  if (MATCH_GUID((lpData->guidInfo), GUID_GetDriverInfo2))
  {
    ASSERT(NULL != lpData);
    ASSERT(NULL != lpData->lpvData);

    // Is this a call to GetDriverInfo2 or DDStereoMode?
 if (((DD_GETDRIVERINFO2DATA*)(lpData->lpvData))->dwMagic
      == D3DGDI2_MAGIC)
 {
      // Yes, it's a call to GetDriverInfo2, fetch the
 // DD_GETDRIVERINFO2DATA data structure.
      DD_GETDRIVERINFO2DATA* pgdi2 = lpData->lpvData;
 ASSERT(NULL != pgdi2);
      // What type of request is this?
      switch (pgdi2->dwType)
      {
        case D3DGDI2_TYPE_GETD3DCAPS8:
        {
          // The runtime is requesting the DX8 D3D caps
          // so copy them over now. It should be noted
          // that the dwExpectedSize field of
          // DD_GETDRIVERINFODATA is not used for
          // GetDriverInfo2 calls and should be ignored.
          size_t copySize = min(
            sizeof(myD3DCaps8), pgdi2->dwExpectedSize);
          memcpy(lpData->lpvData, &myD3DCaps8, copySize);
          lpData->dwActualSize = copySize;
          lpData->ddRVal       = DD_OK;
          return DDHAL_DRIVER_HANDLED;
        }
        default:
          // For any other GetDriverInfo2 types not handled
          // or understood by the driver set a ddRVal of
          // DDERR_CURRENTLYNOTAVAIL and return
          // DDHAL_DRIVER_HANDLED.
          return DDHAL_DRIVER_HANDLED;
      }
    }
    else
    {
      // It must be a call to request for stereo mode support.
 // Fetch the stereo mode data
      DD_STEREOMODE* pStereoMode = lpData->lpvData;
 ASSERT(NULL != pStereoMode);

      // Process the stereo mode request...
      lpData->dwActualSize = sizeof(DD_STEREOMODE);
      lpData->ddRVal       = DD_OK;
      return DDHAL_DRIVER_HANDLED;
    }
  }

  // Handle any other device GUIDs...

} // DdGetDriverInfo
```

For more information about D3DCAPS8 and D3DCAPS9, see the DirectX SDK documentation.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_deferred_agp_aware_data">DD_DEFERRED_AGP_AWARE_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_dxversion">DD_DXVERSION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_free_deferred_agp_data">DD_FREE_DEFERRED_AGP_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_getadaptergroupdata">DD_GETADAPTERGROUPDATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_getd3dquerycountdata">DD_GETD3DQUERYCOUNTDATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_getd3dquerydata">DD_GETD3DQUERYDATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_getddiversiondata">DD_GETDDIVERSIONDATA</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/ns-ddrawint-_dd_getdriverinfodata">DD_GETDRIVERINFODATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_getextendedmodecountdata">DD_GETEXTENDEDMODECOUNTDATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_getextendedmodedata">DD_GETEXTENDEDMODEDATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_getformatcountdata">DD_GETFORMATCOUNTDATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_getformatdata">DD_GETFORMATDATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_multisamplequalitylevelsdata">DD_MULTISAMPLEQUALITYLEVELSDATA</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/ns-ddrawint-_dd_stereomode">DD_STEREOMODE</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/nc-ddrawint-pdd_getdriverinfo">DdGetDriverInfo</a>
 

 

