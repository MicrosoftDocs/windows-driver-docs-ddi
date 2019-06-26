---
UID: NE:d3dkmdt._D3DKMDT_MONITOR_CONNECTIVITY_CHECKS
title: _D3DKMDT_MONITOR_CONNECTIVITY_CHECKS (d3dkmdt.h)
description: The D3DKMDT_MONITOR_CONNECTIVITY_CHECKS enumerated type indicates whether the DxgkDdiCommitVidPn function should verify that certain video outputs have connected monitors.
old-location: display\d3dkmdt_monitor_connectivity_checks.htm
tech.root: display
ms.assetid: 8a32fef1-e404-478d-8b99-064ed456e37c
ms.date: 05/10/2018
ms.keywords: D3DKMDT_MCC_ENFORCE, D3DKMDT_MCC_IGNORE, D3DKMDT_MCC_UNINITIALIZED, D3DKMDT_MONITOR_CONNECTIVITY_CHECKS, D3DKMDT_MONITOR_CONNECTIVITY_CHECKS enumeration [Display Devices], DmEnums_ac54453d-cc4d-4ea7-ad10-943389a837d7.xml, _D3DKMDT_MONITOR_CONNECTIVITY_CHECKS, d3dkmdt/D3DKMDT_MCC_ENFORCE, d3dkmdt/D3DKMDT_MCC_IGNORE, d3dkmdt/D3DKMDT_MCC_UNINITIALIZED, d3dkmdt/D3DKMDT_MONITOR_CONNECTIVITY_CHECKS, display.d3dkmdt_monitor_connectivity_checks
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmdt.h
api_name:
- D3DKMDT_MONITOR_CONNECTIVITY_CHECKS
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_MONITOR_CONNECTIVITY_CHECKS
---

# _D3DKMDT_MONITOR_CONNECTIVITY_CHECKS enumeration


## -description


The D3DKMDT_MONITOR_CONNECTIVITY_CHECKS enumerated type indicates whether the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_commitvidpn">DxgkDdiCommitVidPn</a> function should verify that certain video outputs have connected monitors.


## -enum-fields




### -field D3DKMDT_MCC_UNINITIALIZED

Indicates that a variable of type D3DKMDT_MONITOR_CONNECTIVITY_CHECKS has not yet been assigned a meaningful value.


### -field D3DKMDT_MCC_IGNORE

Indicates that <b>DxgkDdiCommitVidPn</b> does not need to verify that monitors are connected.


### -field D3DKMDT_MCC_ENFORCE

Indicates that <b>DxgkDdiCommitVidPn</b> must verify that monitors are connected.


## -remarks



The <b>MonitorConnectivityChecks</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_commitvidpn">DXGKARG_COMMITVIDPN</a> structure is a D3DKMDT_MONITOR_CONNECTIVITY_CHECKS value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_commitvidpn">DxgkDdiCommitVidPn</a>
 

 

