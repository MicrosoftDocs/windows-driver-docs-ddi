---
UID: NF:hbaapi.HBA_LoadLibrary
title: HBA_LoadLibrary function
author: windows-driver-content
description: The HBA_LoadLibrary routine loads and initializes the system-supplied fibre channel HBA API library.
old-location: storage\hba_loadlibrary.htm
old-project: storage
ms.assetid: f71be39c-4b0c-47fc-a9d5-dfe69d8b11f2
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: HBA_LoadLibrary
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
req.alt-api: HBA_LoadLibrary
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

# HBA_LoadLibrary function



## -description
The <b>HBA_LoadLibrary</b> routine loads and initializes the system-supplied fibre channel HBA API library. 



## -syntax

````
HBA_STATUS HBA_API HBA_LoadLibrary(void);
````


## -parameters


## -returns
The <b>HBA_LoadLibrary</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_LoadLibrary</b> returns one of the following qualifiers.
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>Returned if the library loaded properly. 
<dl>
<dt><b>HBA_STATUS_ERROR_ALREADY_LOADED</b></dt>
</dl>Returned if the library is already loaded.
<dl>
<dt><b>HBA_STATUS_ERROR_INCOMPATIBLE</b></dt>
</dl>Returned if <b>HBA_LoadLibrary</b> discovered incompatibilities between the library and the associated HBA drivers. 
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>Returned if an unspecified error occurred that prevented the library from loading. 

 

The <b>HBA_LoadLibrary</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_LoadLibrary</b> returns one of the following qualifiers.
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>Returned if the library loaded properly. 
<dl>
<dt><b>HBA_STATUS_ERROR_ALREADY_LOADED</b></dt>
</dl>Returned if the library is already loaded.
<dl>
<dt><b>HBA_STATUS_ERROR_INCOMPATIBLE</b></dt>
</dl>Returned if <b>HBA_LoadLibrary</b> discovered incompatibilities between the library and the associated HBA drivers. 
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>Returned if an unspecified error occurred that prevented the library from loading. 

 

The <b>HBA_LoadLibrary</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_LoadLibrary</b> returns one of the following qualifiers.
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>Returned if the library loaded properly. 
<dl>
<dt><b>HBA_STATUS_ERROR_ALREADY_LOADED</b></dt>
</dl>Returned if the library is already loaded.
<dl>
<dt><b>HBA_STATUS_ERROR_INCOMPATIBLE</b></dt>
</dl>Returned if <b>HBA_LoadLibrary</b> discovered incompatibilities between the library and the associated HBA drivers. 
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>Returned if an unspecified error occurred that prevented the library from loading. 

 


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_LoadLibrary routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

