---
UID: NF:ndis.NdisCloseAdapter
tech.root: 
title: NdisCloseAdapter
ms.date: 
targetos: Windows
description: 
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndis.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - Kernel32.dll
 - ndis.h
api_name:
 - NdisCloseAdapter
f1_keywords:
 - NdisCloseAdapter
 - ndis/NdisCloseAdapter
dev_langs:
 - c++
helpviewer_keywords:
 - NdisCloseAdapter
---

# NdisCloseAdapter function

## -description

**Note**   NDIS 5. *x* has been deprecated and is superseded by NDIS 6. *x*. For new NDIS driver development, see [Network Drivers Starting with Windows Vista](https://msdn.microsoft.com/library/Ff570021). For information about porting NDIS 5. *x* drivers to NDIS 6. *x*, see [Porting NDIS 5.x Drivers to NDIS 6.0](https://msdn.microsoft.com/library/Ff570059).

**NdisCloseAdapter** releases the binding established and the resources allocated when the protocol called [**NdisOpenAdapter**](ff553673\(v=vs.85\).md).

## Syntax

```cpp
VOID NdisCloseAdapter(
  _Out_ PNDIS_STATUS Status,
  _In_  NDIS_HANDLE  NdisBindingHandle
);
```

## -parameters

  - *Status* \[out\]  
    Pointer to a caller-supplied variable in which this function returns the status of the close operation, which can be one of the following values:
    
      - NDIS\_STATUS\_SUCCESS  
        The binding was closed and all resources pertaining to that binding have been released.
    
      - NDIS\_STATUS\_PENDING  
        A close-adapter request is being handled asynchronously, and the caller's [**ProtocolCloseAdapterComplete**](ff562502\(v=vs.85\).md) function will be called when the close operation is done.

  - *NdisBindingHandle* 

### -param Status [out]  

Pointer to a caller-supplied variable in which this function returns the status of the close operation, which can be one of the following values:

- NDIS\_STATUS\_SUCCESS  
  The binding was closed and all resources pertaining to that binding have been released.

- NDIS\_STATUS\_PENDING  
  A close-adapter request is being handled asynchronously, and the caller's [**ProtocolCloseAdapterComplete**](ff562502\(v=vs.85\).md) function will be called when the close operation is done.

### -param NdisBindingHandle [in]

Specifies the handle returned by **NdisOpenAdapter** that identifies the virtual adapter or NIC to be closed.

## Return value

None

## -remarks

A protocol driver typically calls **NdisCloseAdapter** from its [**ProtocolUnbindAdapter**](ff563260\(v=vs.85\).md) function. It can also call **NdisCloseAdapter** from its [**ProtocolBindAdapter**](ff562465\(v=vs.85\).md) function, for example, if it failed to set an OID value after calling [**NdisOpenAdapter**](ff553673\(v=vs.85\).md) to set up a binding.

As soon as a protocol calls **NdisCloseAdapter**, the handle at *NdisBindingHandle* should be considered invalid by the caller. It is a programming error to pass this handle in any subsequent call to an *NdisXxx* function.

## Requirements

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Target platform</p></td>
<td><a href="https://go.microsoft.com/fwlink/p/?linkid=531356">Universal</a></td>
</tr>
<tr class="even">
<td><p>Version</p></td>
<td><p>Not supported for NDIS 6.0 drivers in Windows Vista. Use NdisCloseAdapterEx instead. Supported for NDIS 5.1 drivers in Windows Vista and Windows XP.</p></td>
</tr>
<tr class="odd">
<td><p>Header</p></td>
<td>Ndis.h (include Ndis.h)</td>
</tr>
<tr class="even">
<td><p>Library</p></td>
<td>Ndis.lib</td>
</tr>
<tr class="odd">
<td><p>IRQL</p></td>
<td><p>PASSIVE_LEVEL.</p></td>
</tr>
</tbody>
</table>

## -see-also

[**NdisCompleteUnbindAdapter**](ff551048\(v=vs.85\).md)

[**NdisOpenAdapter**](ff553673\(v=vs.85\).md)

[**ProtocolCloseAdapterComplete**](ff562502\(v=vs.85\).md)

[**ProtocolUnbindAdapter**](ff563260\(v=vs.85\).md)

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=documentation%20feedback%20%5Bnetxp\\netxp%5D:%20ndiscloseadapter%20function%20%20release:%20\(6/19/2017\)&body=%0a%0aprivacy%20statement%0a%0awe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20we%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20while%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0a%0afor%20more%20info%20about%20microsoft's%20privacy%20policy,%20see%20https://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")
