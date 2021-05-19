---
UID: NS:wwan._WWAN_TLV_IE
tech.root: 
title: WWAN_TLV_IE
ms.date: 
targetos: Windows
description: 
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wwan.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
targetos: Windows
req.typenames: WWAN_TLV_IE, *PWWAN_TLV_IE
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_TLV_IE
 - PWWAN_TLV_IE
 - WWAN_TLV_IE
f1_keywords:
 - _WWAN_TLV_IE
 - wwan/_WWAN_TLV_IE
 - PWWAN_TLV_IE
 - wwan/PWWAN_TLV_IE
 - WWAN_TLV_IE
 - wwan/WWAN_TLV_IE
dev_langs:
 - c++
---

## -description

A variable-sized data structure that is capable of exchanging a wide range of information between a WWAN host and a WWAN device.

## -struct-fields

### -field Type

A two-octet IE type value identifying the information element that follows. 

### -field Reserved

Unused and reserved byte. Must set to zero.

### -field PaddingLength

Length of the Padding field in octets. Must be 0, 1, 2, or 3.

### -field DataLength

The length of the *Data* field in octets.

## -remarks

The padding is to ensure that the entire size of the structure is a multiple of the size of a DWORD.

## -see-also
