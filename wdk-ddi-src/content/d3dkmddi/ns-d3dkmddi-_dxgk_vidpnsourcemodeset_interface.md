---
UID: NS:d3dkmddi._DXGK_VIDPNSOURCEMODESET_INTERFACE
title: "_DXGK_VIDPNSOURCEMODESET_INTERFACE"
author: windows-driver-content
description: The DXGK_VIDPNSOURCEMODESET_INTERFACE structure contains pointers to functions that belong to the VidPn Source Mode Set interface, which is implemented by the video present network (VidPN) manager.
old-location: display\dxgk_vidpnsourcemodeset_interface.htm
old-project: display
ms.assetid: c608643f-e791-44b8-8719-4e98e10fa7b0
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGK_VIDPNSOURCEMODESET_INTERFACE, DXGK_VIDPNSOURCEMODESET_INTERFACE structure [Display Devices], DmStructs_8e8b4b99-8121-4cff-9d1b-f88a9041e7cd.xml, _DXGK_VIDPNSOURCEMODESET_INTERFACE, d3dkmddi/DXGK_VIDPNSOURCEMODESET_INTERFACE, display.dxgk_vidpnsourcemodeset_interface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_VIDPNSOURCEMODESET_INTERFACE
product: Windows
targetos: Windows
req.typenames: DXGK_VIDPNSOURCEMODESET_INTERFACE
---

# _DXGK_VIDPNSOURCEMODESET_INTERFACE structure


## -description


The DXGK_VIDPNSOURCEMODESET_INTERFACE structure contains pointers to functions that belong to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570558">VidPn Source Mode Set interface</a>, which is implemented by the video present network (VidPN) manager.


## -syntax


````
typedef struct _DXGK_VIDPNSOURCEMODESET_INTERFACE {
  DXGKDDI_VIDPNSOURCEMODESET_GETNUMMODES           pfnGetNumModes;
  DXGKDDI_VIDPNSOURCEMODESET_ACQUIREFIRSTMODEINFO  pfnAcquireFirstModeInfo;
  DXGKDDI_VIDPNSOURCEMODESET_ACQUIRENEXTMODEINFO   pfnAcquireNextModeInfo;
  DXGKDDI_VIDPNSOURCEMODESET_ACQUIREPINNEDMODEINFO pfnAcquirePinnedModeInfo;
  DXGKDDI_VIDPNSOURCEMODESET_RELEASEMODEINFO       pfnReleaseModeInfo;
  DXGKDDI_VIDPNSOURCEMODESET_CREATENEWMODEINFO     pfnCreateNewModeInfo;
  DXGKDDI_VIDPNSOURCEMODESET_ADDMODE               pfnAddMode;
  DXGKDDI_VIDPNSOURCEMODESET_PINMODE               pfnPinMode;
} DXGK_VIDPNSOURCEMODESET_INTERFACE;
````


## -struct-fields




### -field pfnGetNumModes

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_getnummodes.md">pfnGetNumModes</a> function.


### -field pfnAcquireFirstModeInfo

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirefirstmodeinfo.md">pfnAcquireFirstModeInfo</a> function.


### -field pfnAcquireNextModeInfo

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirenextmodeinfo.md">pfnAcquireNextModeInfo</a> function.


### -field pfnAcquirePinnedModeInfo

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirepinnedmodeinfo.md">pfnAcquirePinnedModeInfo</a> function.


### -field pfnReleaseModeInfo

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_releasemodeinfo.md">pfnReleaseModeInfo</a> function.


### -field pfnCreateNewModeInfo

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_createnewmodeinfo.md">pfnCreateNewModeInfo</a> function.


### -field pfnAddMode

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_addmode.md">pfnAddMode</a> function.


### -field pfnPinMode

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_pinmode.md">pfnPinMode</a> function.


## -remarks



The display miniport driver calls the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_acquiresourcemodeset.md">pfnAcquireSourceModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570556">VidPn interface</a> to obtain a handle to a VidPN source mode set object and a pointer to a DXGK_VIDPNSOURCEMODESET_INTERFACE structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the VidPN source mode set object.




## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpntargetmodeset_interface.md">DXGK_VIDPNTARGETMODESET_INTERFACE</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_acquiresourcemodeset.md">pfnAcquireSourceModeSet</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_source_mode.md">D3DKMDT_VIDPN_SOURCE_MODE</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_monitorsourcemodeset_interface.md">DXGK_MONITORSOURCEMODESET_INTERFACE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_VIDPNSOURCEMODESET_INTERFACE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

