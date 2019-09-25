---
UID: NF:wdfrequest.WdfRequestGetRequestorMode
title: WdfRequestGetRequestorMode function (wdfrequest.h)
description: The WdfRequestGetRequestorMode method returns the processor access mode of the originator of a specified I/O request.
old-location: wdf\wdfrequestgetrequestormode.htm
tech.root: wdf
ms.assetid: 63fc77c8-756c-4872-b608-539d8419154b
ms.date: 02/26/2018
ms.keywords: DFRequestObjectRef_3c672bff-3d8a-402a-8a0c-19eb4d39e37e.xml, WdfRequestGetRequestorMode, WdfRequestGetRequestorMode method, kmdf.wdfrequestgetrequestormode, wdf.wdfrequestgetrequestormode, wdfrequest/WdfRequestGetRequestorMode
ms.topic: function
f1_keywords:
 - "wdfrequest/WdfRequestGetRequestorMode"
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfRequestGetRequestorMode
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRequestGetRequestorMode function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRequestGetRequestorMode</b> method returns the processor access mode of the originator of a specified I/O request.


## -parameters




### -param Request [in]

A handle to a framework request object.


## -returns



<b>WdfRequestGetRequestorMode</b> returns <b>KernelMode</b> if the originator of the I/O request is executing in kernel mode. Otherwise, this method returns <b>UserMode</b>. The <b>KernelMode</b> and <b>UserMode</b> constants are defined in <i>wdm.h</i>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about <b>WdfRequestGetRequestorMode</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/obtaining-information-about-an-i-o-request">Obtaining Information About an I/O Request</a>.


#### Examples

The following code example is from the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/sample-kmdf-drivers">NDISProt</a> sample driver. This example checks for a valid MAC address if the I/O request came from a user-mode application.

```cpp
//
// To prevent applications from sending packets with spoofed MAC address,
// perform the following check to make sure the source address 
// in the packet is the same as the current MAC address of the NIC.
//
if ((WdfRequestGetRequestorMode(Request) == UserMode) && 
    !NPROT_MEM_CMP(pEthHeader->SrcAddr, pOpenContext->CurrentAddress, NPROT_MAC_ADDR_LEN))
{
    DEBUGP(DL_WARN, ("Write: Failing with invalid Source address"));
    NtStatus = STATUS_INVALID_PARAMETER;
    break;
}
```


