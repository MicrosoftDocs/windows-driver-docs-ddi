---
UID: NF:ndis.NdisFGetOptionalSwitchHandlers
title: NdisFGetOptionalSwitchHandlers function
author: windows-driver-content
description: Hyper-V extensible switch extensions call the NdisFGetOptionalSwitchHandlers function to obtain a list of pointers to the Hyper-V extensible switch handler functions.
old-location: netvista\ndisfgetoptionalswitchhandlers.htm
old-project: netvista
ms.assetid: bf034ecd-5c1b-4117-a7b0-bcca3971386b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisFGetOptionalSwitchHandlers function [Network Drivers Starting with Windows Vista], NdisFGetOptionalSwitchHandlers, netvista.ndisfgetoptionalswitchhandlers, ndis/NdisFGetOptionalSwitchHandlers
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisFGetOptionalSwitchHandlers
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisFGetOptionalSwitchHandlers function


## -description



Hyper-V extensible switch extensions call the <b>NdisFGetOptionalSwitchHandlers</b> function to obtain a list of pointers to the Hyper-V extensible switch handler functions.






## -syntax


````
NDIS_STATUS NdisFGetOptionalSwitchHandlers(
  _In_    NDIS_HANDLE                    NdisFilterHandle,
  _Out_   PNDIS_SWITCH_CONTEXT           NdisSwitchContext,
  _Inout_ PNDIS_SWITCH_OPTIONAL_HANDLERS NdisSwitchHandlers
);
````


## -parameters




### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. When NDIS called the extension's  <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function, it passed this handle in the <i>NdisFilterHandle</i> parameter.


### -param NdisSwitchContext [out]

A pointer to the NDIS_SWITCH_CONTEXT value that identifies the extensible switch module to which the extension is attached. When  the  extension calls an extensible switch  handler  function, it must set the     <i>NdisSwitchContext</i> parameter to the value of this handle.


### -param NdisSwitchHandlers [in, out]

A pointer to a caller-allocated  <a href="..\ndis\ns-ndis-_ndis_switch_optional_handlers.md">NDIS_SWITCH_OPTIONAL_HANDLERS</a> structure. If the call succeeds, this structure will contain a list of pointers to the extensible switch handler functions.

For more information about these handler functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh598172">Hyper-V Extensible Switch Handler Functions</a>.

<div class="alert"><b>Note</b>  Before the extension calls <b>NdisFGetOptionalSwitchHandlers</b>, it must initialize the <b>Header</b> member of the <a href="..\ndis\ns-ndis-_ndis_switch_optional_handlers.md">NDIS_SWITCH_OPTIONAL_HANDLERS</a> structure.</div>
<div> </div>

## -returns



If the call succeeds, <b>NdisFGetOptionalSwitchHandlers</b> returns NDIS_STATUS_SUCCESS. Otherwise, it returns NDIS_STATUS_NOT_SUPPORTED if the extensible switch extension is not bound to the underlying extensible switch component.






## -remarks



The  extension calls the <b>NdisFGetOptionalSwitchHandlers</b> function from its <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function. 

If the extension is installed with multiple <b>FilterMediaTypes</b> INF entries, the call to <b>NdisFGetOptionalSwitchHandlers</b> lets the extension  determine whether it is bound and attached to the driver stack for either the extensible switch or a physical network adapter. If the call returns NDIS_STATUS_SUCCESS, the extension is attached within the extensible switch driver stack. If the call returns NDIS_STATUS_NOT_SUPPORTED, the extension is attached within the driver stack for a physical network adapter.

For more information about <b>FilterMediaTypes</b> INF entries for extensible switch extensions, see <a href="https://msdn.microsoft.com/378F619A-C799-4330-A388-9955A67251F8">INF Requirements for Hyper-V Extensible Switch Extensions</a>.




## -see-also

<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>



<a href="..\ndis\ns-ndis-_ndis_switch_optional_handlers.md">NDIS_SWITCH_OPTIONAL_HANDLERS</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFGetOptionalSwitchHandlers function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

