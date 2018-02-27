---
UID: NE:ks.VARENUM
title: VARENUM
author: windows-driver-content
description: "."
old-location: stream\varenum.htm
old-project: stream
ms.assetid: 00F015F4-708F-4272-A903-56C44DC6646E
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: VARENUM, VARENUM enumeration [Streaming Media Devices], VT_ARRAY, VT_BLOB, VT_BLOB_OBJECT, VT_BOOL, VT_BSTR, VT_BYREF, VT_CARRAY, VT_CF, VT_CLSID, VT_CY, VT_DATE, VT_DECIMAL, VT_DISPATCH, VT_EMPTY, VT_ERROR, VT_FILETIME, VT_HRESULT, VT_I1, VT_I2, VT_I4, VT_I8, VT_ILLEGAL, VT_ILLEGALMASKED, VT_INT, VT_LPSTR, VT_LPWSTR, VT_NULL, VT_PTR, VT_R4, VT_R8, VT_RESERVED, VT_SAFEARRAY, VT_STORAGE, VT_STORED_OBJECT, VT_STREAM, VT_STREAMED_OBJECT, VT_TYPEMASK, VT_UI1, VT_UI2, VT_UI4, VT_UI8, VT_UINT, VT_UNKNOWN, VT_USERDEFINED, VT_VARIANT, VT_VECTOR, VT_VOID, ks/ VT_RESERVED, ks/ VT_VECTOR, ks/VARENUM, ks/VT_ARRAY, ks/VT_BLOB, ks/VT_BLOB_OBJECT, ks/VT_BOOL, ks/VT_BSTR, ks/VT_BYREF, ks/VT_CARRAY, ks/VT_CF, ks/VT_CLSID, ks/VT_CY, ks/VT_DATE, ks/VT_DECIMAL, ks/VT_DISPATCH, ks/VT_EMPTY, ks/VT_ERROR, ks/VT_FILETIME, ks/VT_HRESULT, ks/VT_I1, ks/VT_I2, ks/VT_I4, ks/VT_I8, ks/VT_ILLEGAL, ks/VT_ILLEGALMASKED, ks/VT_INT, ks/VT_LPSTR, ks/VT_LPWSTR, ks/VT_NULL, ks/VT_PTR, ks/VT_R4, ks/VT_R8, ks/VT_SAFEARRAY, ks/VT_STORAGE, ks/VT_STORED_OBJECT, ks/VT_STREAM, ks/VT_STREAMED_OBJECT, ks/VT_TYPEMASK, ks/VT_UI1, ks/VT_UI2, ks/VT_UI4, ks/VT_UI8, ks/VT_UINT, ks/VT_UNKNOWN, ks/VT_USERDEFINED, ks/VT_VARIANT, ks/VT_VOID, stream.varenum
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ks.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ks.h
apiname:
-	VARENUM
product: Windows
targetos: Windows
req.typenames: 
---

# VARENUM enumeration


## -description





## -syntax


````
enum VARENUM {
  VT_EMPTY            = 0, 
  VT_NULL             = 1, 
  VT_I2               = 2, 
  VT_I4               = 3, 
  VT_R4               = 4, 
  VT_R8               = 5, 
  VT_CY               = 6, 
  VT_DATE             = 7, 
  VT_BSTR             = 8, 
  VT_DISPATCH         = 9, 
  VT_ERROR            = 10, 
  VT_BOOL             = 11, 
  VT_VARIANT          = 12, 
  VT_UNKNOWN          = 13, 
  VT_DECIMAL          = 14, 
  VT_I1               = 16, 
  VT_UI1              = 17, 
  VT_UI2              = 18, 
  VT_UI4              = 19, 
  VT_I8               = 20, 
  VT_UI8              = 21, 
  VT_INT              = 22, 
  VT_UINT             = 23, 
  VT_VOID             = 24, 
  VT_HRESULT          = 25, 
  VT_PTR              = 26, 
  VT_SAFEARRAY        = 27, 
  VT_CARRAY           = 28, 
  VT_USERDEFINED      = 29, 
  VT_LPSTR            = 30, 
  VT_LPWSTR           = 31, 
  VT_FILETIME         = 64, 
  VT_BLOB             = 65, 
  VT_STREAM           = 66, 
  VT_STORAGE          = 67, 
  VT_STREAMED_OBJECT  = 68, 
  VT_STORED_OBJECT    = 69, 
  VT_BLOB_OBJECT      = 70, 
  VT_CF               = 71, 
  VT_CLSID            = 72, 
   VT_VECTOR          = 0x1000, 
  VT_ARRAY            = 0x2000, 
  VT_BYREF            = 0x4000, 
   VT_RESERVED        = 0x8000, 
  VT_ILLEGAL          = 0xffff, 
  VT_ILLEGALMASKED    = 0xfff, 
  VT_TYPEMASK         = 0xfff 

};
````


## -enum-fields




### -field VT_EMPTY


### -field VT_NULL


### -field VT_I2


### -field VT_I4


### -field VT_R4


### -field VT_R8


### -field VT_CY


### -field VT_DATE


### -field VT_BSTR


### -field VT_DISPATCH


### -field VT_ERROR


### -field VT_BOOL


### -field VT_VARIANT


### -field VT_UNKNOWN


### -field VT_DECIMAL


### -field VT_I1


### -field VT_UI1


### -field VT_UI2


### -field VT_UI4


### -field VT_I8


### -field VT_UI8


### -field VT_INT


### -field VT_UINT


### -field VT_VOID


### -field VT_HRESULT


### -field VT_PTR


### -field VT_SAFEARRAY


### -field VT_CARRAY


### -field VT_USERDEFINED


### -field VT_LPSTR


### -field VT_LPWSTR


### -field VT_FILETIME


### -field VT_BLOB


### -field VT_STREAM


### -field VT_STORAGE


### -field VT_STREAMED_OBJECT


### -field VT_STORED_OBJECT


### -field VT_BLOB_OBJECT


### -field VT_CF


### -field VT_CLSID


### -field VT_VECTOR


### -field VT_ARRAY


### -field VT_BYREF


### -field VT_RESERVED


### -field VT_ILLEGAL


### -field VT_ILLEGALMASKED


### -field VT_TYPEMASK

