---
UID: NF:pktmonclntk.PktMonClntSetComponentProperty
tech.root: netvista
title: PktMonClntSetComponentProperty
ms.date: 02/19/2025
targetos: Windows
description: The PktMonClntSetComponentProperty function sets a property for a specific component.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: pktmonclntk.h
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
 - HeaderDef
api_location:
 - pktmonclntk.h
api_name:
 - PktMonClntSetComponentProperty
f1_keywords:
 - PktMonClntSetComponentProperty
 - pktmonclntk/PktMonClntSetComponentProperty
dev_langs:
 - c++
helpviewer_keywords:
 - PktMonClntSetComponentProperty
---

## -description

The **PktMonClntSetComponentProperty** function sets a property for a specific component.

## -parameters

### -param CompContext

Pointer to the **[PKTMON_COMPONENT_CONTEXT](ns-pktmonclntk-pktmon_component_context.md)** structure that holds the context for the component.

### -param CompProperty

Pointer to the **[PKTMON_COMPONENT_PROPERTY](ns-pktmonclntk-pktmon_component_property.md)** structure that describes the property to be set.

## -returns

If the function succeeds, it returns `STATUS_SUCCESS`. Otherwise, it returns a `NTSTATUS` error code.

## -remarks

Use the **PktMonClntSetComponentProperty** function to set various properties for a component. Call this function once for each property. These properties provide detailed information about the component, such as its interface ID, name, etc. You can display the properties of the components using the `pktmon` command:

```cmd
Pktmon.exe list -a
```

The properties are defined in the **PKTMON_COMPONENT_PROPERTY** structure and can include interface indices, GUIDs, MAC addresses, and other relevant information. Each property is identified by an **Id** from the **PKTMON_COMPONENT_PROPERTY_ID** enumeration.

## -see-also

- **[PKTMON_COMPONENT_CONTEXT](ns-pktmonclntk-pktmon_component_context.md)**
- **[PKTMON_COMPONENT_PROPERTY](ns-pktmonclntk-pktmon_component_property.md)**

### Example

```cpp
NTSTATUS PktMonApiTstSetComponentProperties()
{
    NTSTATUS status = STATUS_SUCCESS;
    PKTMON_COMPONENT_PROPERTY compProp = {0};

    compProp.Id = PktMonCompProp_IfIndex;
    compProp.IfIndex = 100;
    status = PktMonClntSetComponentProperty(&PktMonComp, &compProp);
    if (STATUS_SUCCESS != status)
    {
        // Log error
        return status;
    }

    return status;
}
```
