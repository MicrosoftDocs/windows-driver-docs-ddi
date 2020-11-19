---
UID: NF:ndis.NdisInitializeString
title: NdisInitializeString function (ndis.h)
description: The NdisInitializeString function allocates storage for and initializes a counted string in the system-default character set.
old-location: netvista\ndisinitializestring.htm
tech.root: netvista
ms.assetid: c6945d7d-5152-4968-a628-7850b8083a82
ms.date: 11/18/2020
keywords: ["NdisInitializeString function"]
ms.keywords: NdisInitializeString, NdisInitializeString function [Network Drivers Starting with Windows Vista], ndis/NdisInitializeString, ndis_string_ref_886eff5e-5f5a-49f2-91d3-e87128cf0542.xml, netvista.ndisinitializestring
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlInitUnicodeString  or RTL_CONSTANT_STRING or   DECLARE_CONST_UNICODE_STRING (see ntdef.h) instead.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisInitializeString
 - ndis/NdisInitializeString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisInitializeString
---

# NdisInitializeString function


## -description

The **NdisInitializeString** function allocates storage for and initializes a counted string in the system-default character set.

## -parameters

### -param Destination

A pointer to an NDIS_STRING with a **NULL** buffer. On return from this function, the NDIS_STRING contains an initialized, counted string. For Windows 2000 and later, NDIS defines the NDIS_STRING type as a [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) type.

### -param Source

A pointer to a null-terminated string with which to initialize the counted string. *SourceString* must not be **NULL**.

## -remarks

**NdisInitializeString** sets the **Length** and **MaximumLength** members of NDIS_STRING for the destination string and terminates the destination string with zero. For Windows 2000 and later drivers,**NdisInitializeString** converts the supplied source string to Unicode characters.

*SourceString* must not be **NULL**.

The buffer allocated by **NdisInitializeString** should be released with the [NdisFreeString](/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreestring) function.

## -see-also

[ANSI_STRING](/windows/win32/api/ntdef/ns-ntdef-string)



[DriverEntry of NDIS Protocol
   Drivers](/previous-versions/windows/embedded/gg156036(v=winembedded.80))



[MiniportInitializeEx](/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize)



[RtlAnsiStringToUnicodeString](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlansistringtounicodestring)



[RtlEqualUnicodeString](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlequalunicodestring)



[RtlFreeAnsiString](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfreeansistring)



[RtlFreeUnicodeString](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfreeunicodestring)



[RtlInitString](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitstring)



[RtlInitUnicodeString](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitunicodestring)



[RtlUnicodeStringToAnsiString](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlunicodestringtoansistring)



[UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)