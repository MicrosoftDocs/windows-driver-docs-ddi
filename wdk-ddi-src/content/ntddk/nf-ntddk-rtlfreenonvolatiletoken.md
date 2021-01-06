---
UID: NF:ntddk.RtlFreeNonVolatileToken
title: RtlFreeNonVolatileToken function (ntddk.h)
description: The routine RtlFreeNonVolatileToken is a cleanup function for the opaque NvToken which is given by a successful call to RtlGetNonVolatileToken.
old-location: ifsk\rtlfreenonvolatiletoken.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RtlFreeNonVolatileToken function"]
ms.keywords: RtlFreeNonVolatileToken, RtlFreeNonVolatileToken routine [Installable File System Drivers], ifsk.rtlfreenonvolatiletoken, ntddk/RtlFreeNonVolatileToken
req.header: ntddk.h
req.include-header: Winnt.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr: None supported
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlFreeNonVolatileToken
 - ntddk/RtlFreeNonVolatileToken
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - RtlFreeNonVolatileToken
---

# RtlFreeNonVolatileToken function


## -description

The routine <b>RtlFreeNonVolatileToken</b> is a cleanup function for the opaque <b>NvToken</b> which is given by a successful
    call to <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlgetnonvolatiletoken">RtlGetNonVolatileToken</a>.

## -parameters

### -param NvToken 

[in]
 A pointer to an opaque structure that has
        information about various properties of the non-volatile memory region which <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlgetnonvolatiletoken">RtlGetNonVolatileToken</a> had returned.

## -returns

The routine <b>RtlFreeNonVolatileToken</b> returns one of the status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
<b>NvToken</b> is an invalid pointer or token.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The request was successful.

</td>
</tr>
</table>

## -remarks

This routine is currently not supported for Windows Server until the next major release of Windows Server.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtldrainnonvolatileflush">RtlDrainNonVolatileFlush</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlflushnonvolatilememory">
RtlFlushNonVolatileMemory</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlflushnonvolatilememoryranges">RtlFlushNonVolatileMemoryRanges</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlgetnonvolatiletoken">RtlGetNonVolatileToken</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlwritenonvolatilememory">RtlWriteNonVolatileMemory</a>
