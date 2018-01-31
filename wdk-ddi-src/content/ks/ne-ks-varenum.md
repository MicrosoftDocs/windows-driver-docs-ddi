---
UID: NE:ks.VARENUM
title: VARENUM
author: windows-driver-content
description: "."
old-location: stream\varenum.htm
old-project: stream
ms.assetid: 00F015F4-708F-4272-A903-56C44DC6646E
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/VT_STREAM, VT_I4, ks/VT_I4, ks/ VT_VECTOR, VT_UI1, VT_ERROR, ks/VT_CF, VT_CF, VT_TYPEMASK, ks/ VT_RESERVED, ks/VT_ARRAY, VT_ILLEGALMASKED, VT_STORED_OBJECT, VT_I8, VT_UI8, ks/VT_UI1, ks/VT_BLOB, ks/VT_R4, ks/VT_LPSTR, VT_FILETIME, VT_UINT, ks/VT_ILLEGALMASKED, VT_HRESULT, VT_SAFEARRAY, VT_INT, VT_USERDEFINED, ks/VARENUM, ks/VT_VARIANT, VT_DISPATCH, ks/VT_UI2, VT_STREAM, VT_PTR, ks/VT_STORAGE, ks/VT_DISPATCH, VT_RESERVED, ks/VT_FILETIME, VT_BOOL, ks/VT_CY, VT_UI4, ks/VT_HRESULT, VT_R4, ks/VT_R8, ks/VT_TYPEMASK, ks/VT_BSTR, ks/VT_PTR, ks/VT_STORED_OBJECT, ks/VT_ILLEGAL, VT_BSTR, VT_I1, ks/VT_I8, VARENUM enumeration [Streaming Media Devices], VT_DATE, VT_CLSID, VARENUM, ks/VT_UI4, ks/VT_DATE, VT_NULL, stream.varenum, VT_STORAGE, ks/VT_ERROR, ks/VT_UI8, VT_VECTOR, VT_UI2, ks/VT_UINT, ks/VT_EMPTY, ks/VT_VOID, ks/VT_CARRAY, VT_R8, VT_ILLEGAL, VT_LPSTR, VT_DECIMAL, ks/VT_NULL, VT_STREAMED_OBJECT, VT_I2, VT_VARIANT, VT_BLOB_OBJECT, ks/VT_UNKNOWN, VT_EMPTY, ks/VT_BOOL, ks/VT_STREAMED_OBJECT, ks/VT_USERDEFINED, VT_LPWSTR, ks/VT_DECIMAL, ks/VT_INT, VT_CARRAY, VT_BYREF, ks/VT_I1, ks/VT_CLSID, ks/VT_SAFEARRAY, VT_VOID, ks/VT_BYREF, VT_ARRAY, VT_CY, ks/VT_LPWSTR, VT_UNKNOWN, ks/VT_I2, VT_BLOB, ks/VT_BLOB_OBJECT
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




#### - VT_EMPTY



#### - VT_NULL



#### - VT_I2



#### - VT_I4



#### - VT_R4



#### - VT_R8



#### - VT_CY



#### - VT_DATE



#### - VT_BSTR



#### - VT_DISPATCH



#### - VT_ERROR



#### - VT_BOOL



#### - VT_VARIANT



#### - VT_UNKNOWN



#### - VT_DECIMAL



#### - VT_I1



#### - VT_UI1



#### - VT_UI2



#### - VT_UI4



#### - VT_I8



#### - VT_UI8



#### - VT_INT



#### - VT_UINT



#### - VT_VOID



#### - VT_HRESULT



#### - VT_PTR



#### - VT_SAFEARRAY



#### - VT_CARRAY



#### - VT_USERDEFINED



#### - VT_LPSTR



#### - VT_LPWSTR



#### - VT_FILETIME



#### - VT_BLOB



#### - VT_STREAM



#### - VT_STORAGE



#### - VT_STREAMED_OBJECT



#### - VT_STORED_OBJECT



#### - VT_BLOB_OBJECT



#### - VT_CF



#### - VT_CLSID



#### - VT_VECTOR



#### - VT_ARRAY



#### - VT_BYREF



#### - VT_RESERVED



#### - VT_ILLEGAL



#### - VT_ILLEGALMASKED



#### - VT_TYPEMASK


