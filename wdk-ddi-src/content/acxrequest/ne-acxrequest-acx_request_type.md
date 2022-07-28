---
UID: NE:acxrequest._ACX_REQUEST_TYPE
tech.root: audio
title: ACX_REQUEST_TYPE
ms.date: 07/26/2022
targetos: Windows
description:  The ACX_REQUEST_TYPE enumeration describes the possible types of ACX requests.
prerelease: true
req.construct-type: enumeration
req.ddi-compliance: 
req.header: acxrequest.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxrequest.h
api_name:
 - _ACX_REQUEST_TYPE
 - PACX_REQUEST_TYPE
 - ACX_REQUEST_TYPE
f1_keywords:
 - _ACX_REQUEST_TYPE
 - acxrequest/_ACX_REQUEST_TYPE
 - PACX_REQUEST_TYPE
 - acxrequest/PACX_REQUEST_TYPE
 - ACX_REQUEST_TYPE
 - acxrequest/ACX_REQUEST_TYPE
dev_langs:
 - c++
---

## -description

The **ACX_REQUEST_TYPE** enumeration describes the possible types of ACX requests.

## -enum-fields

### -field AcxRequestTypeUnknown

The request type is unknown.

### -field AcxRequestTypeAny

Any Request types is possible.

### -field AcxRequestTypeCreate

This is a create request.

### -field AcxRequestTypeProperty

This is a property request.

### -field AcxRequestTypeMethod

This is a method request.

### -field AcxRequestTypeEvent

This is an event request.

### -field AcxRequestTypeResetState

This is a reset request.

### -field AcxRequestTypeMax

For internal validation, do not use.

## -remarks

### Example

Example usage is shown below.

```cpp

    ACX_REQUEST_TYPE reqType;
    
    {
        ACX_REQUEST_PARAMETERS  params;
        ACX_REQUEST_PARAMETERS_INIT(&params);
        AfxRequest::GetParameters(Request, &params);

        reqType = params.Type;
    }
    
    switch(reqType)
    {
    case AcxRequestTypeProperty:
        AfxHelper::DispatchProperty(GetObjectHandle(), Request, &m_Properties, recorder);
        break;
   
    case AcxRequestTypeMethod:
        AfxHelper::DispatchMethod(GetObjectHandle(), Request, &m_Methods, recorder);
        break;
...

```

## -see-also

- [acxrequest.h header](index.md)
