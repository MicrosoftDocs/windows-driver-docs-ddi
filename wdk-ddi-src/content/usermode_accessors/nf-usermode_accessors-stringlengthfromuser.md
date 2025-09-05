---
UID: NF:usermode_accessors.StringLengthFromUser
tech.root: kernel
title: StringLengthFromUser
ms.date: 07/02/2025
targetos: Windows
description: The StringLengthFromUser function safely calculates the length of a null-terminated string in user-mode memory.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: usermode_accessors.h
req.idl: 
req.include-header: 
req.irql: Less than or equal to APC_LEVEL
req.kmdf-ver: 
req.lib: umaccess.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: See Remarks
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - usermode_accessors.h
api_name:
 - StringLengthFromUser
f1_keywords:
 - StringLengthFromUser
 - usermode_accessors/StringLengthFromUser
dev_langs:
 - c++
helpviewer_keywords:
 - StringLengthFromUser
ai-usage: ai-assisted
---

## -description

The **StringLengthFromUser** function safely calculates the length of a null-terminated string in user-mode memory.

## -parameters

### -param String

[in] A pointer to a null-terminated string in user-mode memory.

## -returns

The function returns the length of the string in characters, not including the terminating null character.

## -remarks

This function provides safe access to calculate the length of a null-terminated string located in user-mode memory. It is designed for use by kernel-mode code that needs to determine the length of strings passed from user-mode applications.

The function ensures that the string address is a valid user-mode address before performing the length calculation. It raises a structured exception if the operation fails, such as when the string address is not a valid user-mode address or is inaccessible.

Unlike standard string functions, this function includes validation to prevent kernel crashes when accessing potentially invalid user-mode pointers. This makes it essential for secure kernel programming when processing user-mode string data.

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**StringLengthFromMode**](nf-usermode_accessors-stringlengthfrommode.md)

[**WideStringLengthFromUser**](nf-usermode_accessors-widestringlengthfromuser.md)
