---
UID: NF:hbaapi.HBA_GetBindingSupport
title: HBA_GetBindingSupport function
author: windows-driver-content
description: The HBA_GetBindingSupport routine retrieves the binding capabilities currently enabled for the specified port.
old-location: storage\hba_getbindingsupport.htm
old-project: storage
ms.assetid: 60542ed9-fbb0-48a3-bc97-ce3db7b4ae10
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: HBA_GetBindingSupport
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HBA_GetBindingSupport
req.alt-loc: Hbaapi.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
req.typenames: HBA_WWNTYPE
---

# HBA_GetBindingSupport function



## -description
The <b>HBA_GetBindingSupport</b> routine retrieves the binding capabilities currently enabled for the specified port.



## -syntax

````
HBA_STATUS HBA_API HBA_GetBindingSupport(
  _In_  HBA_HANDLE          Handle,
  _In_  HBA_WWN             HbaPortWWN,
  _Out_ HBA_BIND_CAPABILITY *Flags
);
````


## -parameters

### -param Handle [in]

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA on which the port is located. 


### -param HbaPortWWN [in]

Contains a 64-bit world-wide name (WWN) that uniquely identifies the local HBA port for which this routine retrieves persistent binding capabilities that are currently enabled. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.


### -param Flags [out]

Contains a bitwise OR of flags associated with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556046">HBA_BIND_TYPE</a> WMI property qualifier that represent the persistent binding capabilities of the port that are currently enabled. 


## -returns
The <b>HBA_GetBindingSupport</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_GetBindingCapability</b> returns one of the following qualifiers.
<dl>
<dt><b>HBA_STATUS_ERROR_ILLEGAL_WWN</b></dt>
</dl>Returned if the adapter does not contain a port with the name <i>HbaPortWWN</i>. 
<dl>
<dt><b>HBA_STATUS_ERROR_NOT_SUPPORTED</b></dt>
</dl>Returned if the adapter does not support persistent bindings. 
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>Returned if an unspecified error occurred that prevented the retrieval of the port attributes.

 


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556046">HBA_BIND_TYPE</a>
</dt>
<dt>
<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_GetBindingSupport routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

