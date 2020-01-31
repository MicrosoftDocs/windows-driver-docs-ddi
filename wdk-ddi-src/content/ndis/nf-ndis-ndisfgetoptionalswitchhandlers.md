---
UID: NF:ndis.NdisFGetOptionalSwitchHandlers
title: NdisFGetOptionalSwitchHandlers function (ndis.h)
description: Hyper-V extensible switch extensions call the NdisFGetOptionalSwitchHandlers function to obtain a list of pointers to the Hyper-V extensible switch handler functions.
old-location: netvista\ndisfgetoptionalswitchhandlers.htm
tech.root: netvista
ms.assetid: bf034ecd-5c1b-4117-a7b0-bcca3971386b
ms.date: 05/02/2018
ms.keywords: NdisFGetOptionalSwitchHandlers, NdisFGetOptionalSwitchHandlers function [Network Drivers Starting with Windows Vista], ndis/NdisFGetOptionalSwitchHandlers, netvista.ndisfgetoptionalswitchhandlers
f1_keywords:
 - "ndis/NdisFGetOptionalSwitchHandlers"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisFGetOptionalSwitchHandlers
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFGetOptionalSwitchHandlers function


## -description



Hyper-V extensible switch extensions call the <b>NdisFGetOptionalSwitchHandlers</b> function to obtain a list of pointers to the Hyper-V extensible switch handler functions.






## -parameters




### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. When NDIS called the extension's  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function, it passed this handle in the <i>NdisFilterHandle</i> parameter.


### -param NdisSwitchContext [out]

A pointer to the NDIS_SWITCH_CONTEXT value that identifies the extensible switch module to which the extension is attached. When  the  extension calls an extensible switch  handler  function, it must set the     <i>NdisSwitchContext</i> parameter to the value of this handle.


### -param NdisSwitchHandlers [in, out]

A pointer to a caller-allocated  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_switch_optional_handlers">NDIS_SWITCH_OPTIONAL_HANDLERS</a> structure. If the call succeeds, this structure will contain a list of pointers to the extensible switch handler functions.

For more information about these handler functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">Hyper-V Extensible Switch Handler Functions</a>.

<div class="alert"><b>Note</b>  Before the extension calls <b>NdisFGetOptionalSwitchHandlers</b>, it must initialize the <b>Header</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_switch_optional_handlers">NDIS_SWITCH_OPTIONAL_HANDLERS</a> structure.</div>
<div> </div>

## -returns



If the call succeeds, <b>NdisFGetOptionalSwitchHandlers</b> returns NDIS_STATUS_SUCCESS. Otherwise, it returns NDIS_STATUS_NOT_SUPPORTED if the extensible switch extension is not bound to the underlying extensible switch component.






## -remarks



The  extension calls the <b>NdisFGetOptionalSwitchHandlers</b> function from its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function. 

If the extension is installed with multiple <b>FilterMediaTypes</b> INF entries, the call to <b>NdisFGetOptionalSwitchHandlers</b> lets the extension  determine whether it is bound and attached to the driver stack for either the extensible switch or a physical network adapter. If the call returns NDIS_STATUS_SUCCESS, the extension is attached within the extensible switch driver stack. If the call returns NDIS_STATUS_NOT_SUPPORTED, the extension is attached within the driver stack for a physical network adapter.

For more information about <b>FilterMediaTypes</b> INF entries for extensible switch extensions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/inf-requirements-for-hyper-v-extensions">INF Requirements for Hyper-V Extensible Switch Extensions</a>.




## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_switch_optional_handlers">NDIS_SWITCH_OPTIONAL_HANDLERS</a>
 

 

