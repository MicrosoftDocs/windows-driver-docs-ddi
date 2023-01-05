---
UID: NF:ndis.NdisIMDeregisterLayeredMiniport
tech.root: netvista
title: NdisIMDeregisterLayeredMiniport
ms.date: 01/04/2023
targetos: Windows
description: NdisIMDeregisterLayeredMiniport releases a previously registered intermediate driver.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndis.h
req.idl: 
req.include-header: Ndis.h
req.irql: PASSIVE_LEVEL
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
 - NdisIMDeregisterLayeredMiniport
f1_keywords:
 - NdisIMDeregisterLayeredMiniport
 - ndis/NdisIMDeregisterLayeredMiniport
dev_langs:
 - c++
helpviewer_keywords:
 - NdisIMDeregisterLayeredMiniport
---

# NdisIMDeregisterLayeredMiniport function

## -description

**Note**   NDIS 5. *x* has been deprecated and is superseded by NDIS 6. *x*. For new NDIS driver development, see [Network Drivers Starting with Windows Vista](../_netvista/index.md). For information about porting NDIS 5. *x* drivers to NDIS 6. *x*, see [Porting NDIS 5.x Drivers to NDIS 6.0](https://msdn.microsoft.com/library/Ff570059).

**NdisIMDeregisterLayeredMiniport** releases a previously registered intermediate driver.

## -parameters

### -param DriverHandle [in]

Specifies the handle returned by [**NdisIMRegisterLayeredMiniport**](nf-ndis-ndisimregisterlayeredminiport.md).

## -remarks

An intermediate driver that called **NdisIMRegisterLayeredMiniport** from its **DriverEntry** routine must call **NdisIMDeregisterLayeredMiniport** when it cleans up the resources it allocated before it is unloaded. If the intermediate driver encounters a fatal initialization error within its **DriverEntry** routine, such as an inability to obtain system resources, it must call **NdisIMDeregisterLayeredMiniport**.

The **NdisIMDeregisterLayeredMiniport** function is the reciprocal of **NdisIMRegisterLayeredMiniport**. An intermediate driver typically calls **NdisIMDeregisterLayeredMiniport** from its *ProtocolUnbindAdapter* function after calling [**NdisDeregisterProtocol**](nf-ndis-ndisderegisterprotocol.md).

- Target platform: [Universal](https://go.microsoft.com/fwlink/p/?linkid=531356)
- Version: Not supported for NDIS 6.0 drivers in Windows Vista. Use <a href="https://msdn.microsoft.com/library/Ff563578"><strong>NdisMDeregisterMiniportDriver</strong></a>instead. Supported for NDIS 5.1 drivers in Windows Vista and Windows XP.

## -see-also

- [**NdisDeregisterProtocolNdisIMRegisterLayeredMiniport**](nf-ndis-ndisimregisterlayeredminiport.md)
