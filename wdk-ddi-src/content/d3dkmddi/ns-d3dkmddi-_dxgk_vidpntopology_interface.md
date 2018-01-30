---
UID: NS:d3dkmddi._DXGK_VIDPNTOPOLOGY_INTERFACE
title: "_DXGK_VIDPNTOPOLOGY_INTERFACE"
author: windows-driver-content
description: The DXGK_VIDPNTOPOLOGY_INTERFACE structure contains pointers to functions that belong to the VidPn Topology interface, which is implemented by the video present network (VidPN) manager.
old-location: display\dxgk_vidpntopology_interface.htm
old-project: display
ms.assetid: 293103cc-217c-4dcb-82c1-971adba564a0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DmStructs_6e2f92a1-beaa-4485-bb27-aff719a693b4.xml, display.dxgk_vidpntopology_interface, d3dkmddi/DXGK_VIDPNTOPOLOGY_INTERFACE, DXGK_VIDPNTOPOLOGY_INTERFACE structure [Display Devices], _DXGK_VIDPNTOPOLOGY_INTERFACE, DXGK_VIDPNTOPOLOGY_INTERFACE
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
-	DXGK_VIDPNTOPOLOGY_INTERFACE
product: Windows
targetos: Windows
req.typenames: DXGK_VIDPNTOPOLOGY_INTERFACE
---

# _DXGK_VIDPNTOPOLOGY_INTERFACE structure


## -description


The DXGK_VIDPNTOPOLOGY_INTERFACE structure contains pointers to functions that belong to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570560">VidPn Topology interface</a>, which is implemented by the video present network (VidPN) manager.


## -syntax


````
typedef struct _DXGK_VIDPNTOPOLOGY_INTERFACE {
  DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHS               pfnGetNumPaths;
  DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHSFROMSOURCE     pfnGetNumPathsFromSource;
  DXGKDDI_VIDPNTOPOLOGY_ENUMPATHTARGETSFROMSOURCE pfnEnumPathTargetsFromSource;
  DXGKDDI_VIDPNTOPOLOGY_GETPATHSOURCEFROMTARGET   pfnGetPathSourceFromTarget;
  DXGKDDI_VIDPNTOPOLOGY_ACQUIREPATHINFO           pfnAcquirePathInfo;
  DXGKDDI_VIDPNTOPOLOGY_ACQUIREFIRSTPATHINFO      pfnAcquireFirstPathInfo;
  DXGKDDI_VIDPNTOPOLOGY_ACQUIRENEXTPATHINFO       pfnAcquireNextPathInfo;
  DXGKDDI_VIDPNTOPOLOGY_UPDATEPATHSUPPORTINFO     pfnUpdatePathSupportInfo;
  DXGKDDI_VIDPNTOPOLOGY_RELEASEPATHINFO           pfnReleasePathInfo;
  DXGKDDI_VIDPNTOPOLOGY_CREATENEWPATHINFO         pfnCreateNewPathInfo;
  DXGKDDI_VIDPNTOPOLOGY_ADDPATH                   pfnAddPath;
  DXGKDDI_VIDPNTOPOLOGY_REMOVEPATH                pfnRemovePath;
} DXGK_VIDPNTOPOLOGY_INTERFACE;
````


## -struct-fields




### -field pfnGetNumPaths

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_getnumpaths.md">pfnGetNumPaths</a> function.


### -field pfnGetNumPathsFromSource

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_getnumpathsfromsource.md">pfnGetNumPathsFromSource</a> function.


### -field pfnEnumPathTargetsFromSource

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_enumpathtargetsfromsource.md">pfnEnumPathTargetsFromSource</a> function.


### -field pfnGetPathSourceFromTarget

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_getpathsourcefromtarget.md">pfnGetPathSourceFromTarget</a> function.


### -field pfnAcquirePathInfo

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_acquirepathinfo.md">pfnAcquirePathInfo</a> function.


### -field pfnAcquireFirstPathInfo

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_acquirefirstpathinfo.md">pfnAcquireFirstPathInfo</a> function.


### -field pfnAcquireNextPathInfo

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_acquirenextpathinfo.md">pfnAcquireNextPathInfo</a> function.


### -field pfnUpdatePathSupportInfo

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_updatepathsupportinfo.md">pfnUpdatePathSupportInfo</a> function.


### -field pfnReleasePathInfo

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_releasepathinfo.md">pfnReleasePathInfo</a> function.


### -field pfnCreateNewPathInfo

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_createnewpathinfo.md">pfnCreateNewPathInfo</a> function.


### -field pfnAddPath


      A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_addpath.md">pfnAddPath</a> function.
     


### -field pfnRemovePath

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_removepath.md">pfnRemovePath</a> function.


## -remarks


The display miniport driver calls the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_gettopology.md">pfnGetTopology</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570556">VidPn interface</a> to obtain a handle to a VidPN topology object and a pointer to a DXGK_VIDPNTOPOLOGY_INTERFACE structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the VidPN topology object.


