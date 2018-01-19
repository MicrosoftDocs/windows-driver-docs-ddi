---
UID: NF:upssvc.UPSInit
title: UPSInit function
author: windows-driver-content
description: The UPSInit function initializes a UPS minidriver, opens communication to the UPS unit, updates the registry, and causes the minidriver to start monitoring the UPS unit.
old-location: battery\upsinit.htm
old-project: battery
ms.assetid: abcb1f9c-3de3-430c-87e0-6648d60ca420
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: UPSInit
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: upssvc.h
req.include-header: Upssvc.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UPSInit
req.alt-loc: Upssvc.h
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
req.typenames: UMDETW_ALLOCATION_USAGE
req.product: Windows 10 or later.
---

# UPSInit function



## -description
The <b>UPSInit</b> function initializes a UPS minidriver, opens communication to the UPS unit, updates the registry, and causes the minidriver to start monitoring the UPS unit.



## -syntax

````
DWORD UPSInit(
   void 
);
````


## -parameters

### -param  

None


## -returns
The <b>UPSInit</b> function returns one of the following DWORD values:
<dl>
<dt><b>UPS_INITOK</b></dt>
</dl>No errors were encountered during initialization. 
<dl>
<dt><b>UPS_INITREGISTRYERROR</b></dt>
</dl>An error occurred while accessing the registry.
<dl>
<dt><b>UPS_INITCOMMOPENERROR</b></dt>
</dl>An error occurred while opening the COM port.
<dl>
<dt><b>UPS_INITCOMMSETUPERROR</b></dt>
</dl>An error occurred while setting up the COM port.
<dl>
<dt><b>UPS_INITUNKNOWNERROR</b></dt>
</dl>An unidentified error occurred.

 


## -remarks
The <b>UPSInit</b> function is the first function exported by a UPS minidriver that is called by the UPS service. The function must complete all initialization operations for the minidriver, including the following:

Opening a communication path to the UPS unit

Determining the initial state of the UPS unit

Updating <a href="https://msdn.microsoft.com/d0d4ef8f-9df1-48a3-b0fc-cea4eb3cdf40">UPS registry entries</a>


Beginning the monitoring of the UPS unit

If the <b>UPSInit</b> function returns a value other than UPS_INITOK, the UPS service immediately calls the <a href="..\upssvc\nf-upssvc-upsstop.md">UPSStop</a> function.


## -see-also
<dl>
<dt>
<a href="..\upssvc\nf-upssvc-upsstop.md">UPSStop</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [battery\battery]:%20UPSInit function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

