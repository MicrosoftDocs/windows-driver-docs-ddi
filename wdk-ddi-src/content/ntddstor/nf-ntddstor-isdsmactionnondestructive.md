---
UID: NF:ntddstor.IsDsmActionNonDestructive
title: IsDsmActionNonDestructive macro
author: windows-driver-content
description: The IsDsmActionNonDestructive macro determines whether a data set management (DSM) action is nondestructive.
tech.root: storage
ms.assetid: a52c39a3-c6a2-4885-9679-5f56531be851
ms.author: windowsdriverdev
ms.date: 08/23/2019
ms.topic: macro
f1_keywords:
 - "ntddstor/IsDsmActionNonDestructive"
ms.keywords: IsDsmActionNonDestructive
req.header: ntddstor.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ntddstor.h
api_name: 
- IsDsmActionNonDestructive
product: 
- Windows
targetos: Windows

---

# IsDsmActionNonDestructive macro

## -description

The **IsDsmActionNonDestructive** macro determines whether a data set management (DSM) action is nondestructive.

## -parameters

### -param _Action

The **DeviceDsmAction_*Xxx*** action to be performed. DSM action values are defined in *ntddstor.h*.

## -remarks

**IsDsmActionNonDestructive** returns **TRUE** if the action is nondestructive or **FALSE** if the action is destructive.

## -see-also