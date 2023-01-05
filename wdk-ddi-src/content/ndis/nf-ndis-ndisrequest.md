---
UID: NF:ndis.NdisRequest
tech.root: netvista
title: NdisRequest
ms.date: 01/04/2023
targetos: Windows
description: NdisRequest forwards a request to the underlying driver that it query the capabilities or status of its NIC or that it set the state of its NIC.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndis.h
req.idl: 
req.include-header: Ndis.h
req.irql: IRQL <= DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: Ndis.lib
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
 - NdisRequest
f1_keywords:
 - NdisRequest
 - ndis/NdisRequest
dev_langs:
 - c++
helpviewer_keywords:
 - NdisRequest
---

# NdisRequest function

## -description

**Note**   NDIS 5. *x* has been deprecated and is superseded by NDIS 6. *x*. For new NDIS driver development, see [Network Drivers Starting with Windows Vista](../_netvista/index.md). For information about porting NDIS 5. *x* drivers to NDIS 6. *x*, see [Porting NDIS 5.x Drivers to NDIS 6.0](https://msdn.microsoft.com/library/Ff570059).

**NdisRequest** forwards a request to the underlying driver that it query the capabilities or status of its NIC or that it set the state of its NIC.

## -parameters

### -param Status [out]

Pointer to a caller-supplied variable that is set on return from this function. The underlying driver determines which NDIS\_STATUS\_*XXX* is returned, but it is usually one of the following values:

- NDIS\_STATUS\_SUCCESS  
  The requested operation completed successfully.

- NDIS\_STATUS\_PENDING  
  The request is being handled asynchronously, and the caller's [**ProtocolRequestComplete**](https://msdn.microsoft.com/library/ff563254\(v=vs.85\)) function will be called when it is completed.

- NDIS\_STATUS\_INVALID\_OID  
  The OID\_*XXX* code specified in the **Oid** member of the NDIS\_REQUEST-structured buffer at *NdisRequest* is invalid or unsupported by the underlying driver.

- NDIS\_STATUS\_INVALID\_LENGTH or NDIS\_STATUS\_BUFFER\_TOO\_SHORT  
  The value specified in the **InformationBufferLength** member of the NDIS\_REQUEST-structured buffer at *NdisRequest* does not match the requirements for the given OID\_*XXX* code. If the information buffer is too small, the **BytesNeeded** member contains the correct value for **InformationBufferLength** on return from **NdisRequest**.

- NDIS\_STATUS\_INVALID\_DATA  
  The data supplied at **InformationBuffer** in the given [**NDIS\_REQUEST**](https://msdn.microsoft.com/library/ff557179\(v=vs.85\)) structure is invalid for the given OID\_*XXX* code.

- NDIS\_STATUS\_NOT\_SUPPORTED or NDIS\_STATUS\_NOT\_RECOGNIZED  
  The underlying driver does not support the requested operation.

- NDIS\_STATUS\_RESOURCES  
  The request could not be satisfied due to a resource shortage. Usually, this return indicates that an attempt to allocate memory was unsuccessful, but it does not necessarily indicate that the same request, submitted later, will be failed for the same reason.

- NDIS\_STATUS\_NOT\_ACCEPTED  
  The underlying driver attempted the requested operation, usually a set, on its NIC but it was failed by the netcard. For example, an attempt to set too many multicast addresses might cause the return of this value.

- NDIS\_STATUS\_CLOSING or NDIS\_STATUS\_CLOSING\_INDICATING  
  The underlying driver failed the requested operation because a close is in progress.

- NDIS\_STATUS\_RESET\_IN\_PROGRESS  
  The underlying NIC driver cannot satisfy the request at this time because it is currently resetting the netcard. The caller's [**ProtocolStatus**](https://msdn.microsoft.com/library/ff563257\(v=vs.85\)) function was or will be called with NDIS\_STATUS\_RESET\_START to indicate that a reset is in progress. This return value does not necessarily indicate that the same request, submitted later, will be failed for the same reason.

- NDIS\_STATUS\_FAILURE  
  This value usually is a nonspecific default, returned when none of the more specific NDIS\_STATUS\_*XXX* caused the underlying driver to fail the request.

### -param NdisBindingHandle [in]

Specifies the handle returned by [**NdisOpenAdapter**](nf-ndis-ndisopenadapter.md) that identifies the target NIC or the virtual adapter of the next-lower driver to which the caller is bound.

### -param NdisRequest [in]

Pointer to a buffered structure specifying the operation requested with a given OID\_ XXX code for either a query or a set.

## -remarks

A protocol driver must allocate sufficient memory for the information buffer associated with the OID\_*XXX* of the operation it will request. The driver also must allocate and set up the buffer at *NdisRequest* before it calls **NdisRequest**. Both buffers must be allocated from nonpaged pool because the underlying driver runs at raised IRQL while processing the request.

For callers layered above an intermediate NDIS driver, **NdisRequest** forwards a request to the next-lower driver that it return information about its own capabilities or directs that driver to handle specific functionality in a caller-determined manner. If the next-lower driver is an NDIS intermediate driver, it can call **NdisRequest** with an OID-specific request of its own before completing the request originally submitted by the higher-level protocol.

Some errors returned at *Status* are recoverable, including the following:

NDIS\_STATUS\_INVALID\_OID

NDIS\_STATUS\_INVALID\_LENGTH

NDIS\_STATUS\_BUFFER\_TOO\_SHORT

NDIS\_STATUS\_INVALID\_DATA

NDIS\_STATUS\_RESOURCES

NDIS\_STATUS\_RESET\_IN\_PROGRESS

That is, a driver can modify the packet at *NdisRequest* appropriately to correct the OID\_*XXX* code and/or the size or contents of the buffer at **InformationBuffer** and resubmit the request packet to **NdisRequest**. The same packet might be satisfied on resubmission to **NdisRequest** if the original call indicated a reset in progress or that a resource shortage, which might be temporary, prevented that request from being carried out.

The NDIS library maintains bindings for underlying miniport drivers. NDIS can return information for binding-specific queries if a given OID is associated with a system-defined medium type for which the system provides a filter library.

For more information about the general and media-specific OIDs and their respective associated information buffers, see [NDIS Object Identifiers](https://msdn.microsoft.com/library/ff557081\(v=vs.85\)).

- Target platform: [Universal](https://go.microsoft.com/fwlink/p/?linkid=531356)
- Version: Not supported for NDIS 6.0 drivers in Windows Vista. Use <a href="https://msdn.microsoft.com/library/Ff563710"><strong>NdisOidRequest</strong></a>instead. Supported for NDIS 5.1 drivers in Windows Vista and Windows XP.

## -see-also

- [**MiniportQueryInformation**](https://msdn.microsoft.com/library/ff550490\(v=vs.85\))
- [**MiniportSetInformation**](https://msdn.microsoft.com/library/ff550530\(v=vs.85\))
- [**NdisOpenAdapter**](nf-ndis-ndisopenadapter.md)
- [**NDIS\_REQUEST**](https://msdn.microsoft.com/library/ff557179\(v=vs.85\))
- [**ProtocolRequestComplete**](https://msdn.microsoft.com/library/ff563254\(v=vs.85\))
- [**ProtocolStatus**](https://msdn.microsoft.com/library/ff563257\(v=vs.85\))
