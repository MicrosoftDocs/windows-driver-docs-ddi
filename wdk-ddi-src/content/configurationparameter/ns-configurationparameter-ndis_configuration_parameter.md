---
UID: NS:configurationparameter._NDIS_CONFIGURATION_PARAMETER
tech.root: netvista
title: NDIS_CONFIGURATION_PARAMETER
ms.date: 07/22/2025
targetos: Windows
description: The NDIS_CONFIGURATION_PARAMETER structure contains the data and type of a named entry in the registry.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: configurationparameter.h
req.include-header: ndis.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers in Windows Vista. Supported for NDIS   5.1 drivers in Windows XP.
req.target-min-winversvr: 
req.target-type: Windows
req.typenames: NDIS_CONFIGURATION_PARAMETER, *PNDIS_CONFIGURATION_PARAMETER
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - configurationparameter.h
api_name:
 - _NDIS_CONFIGURATION_PARAMETER
 - PNDIS_CONFIGURATION_PARAMETER
 - NDIS_CONFIGURATION_PARAMETER
f1_keywords:
 - _NDIS_CONFIGURATION_PARAMETER
 - configurationparameter/_NDIS_CONFIGURATION_PARAMETER
 - PNDIS_CONFIGURATION_PARAMETER
 - configurationparameter/PNDIS_CONFIGURATION_PARAMETER
 - NDIS_CONFIGURATION_PARAMETER
 - configurationparameter/NDIS_CONFIGURATION_PARAMETER
dev_langs:
 - c++
helpviewer_keywords:
 - _NDIS_CONFIGURATION_PARAMETER
---

# _NDIS_CONFIGURATION_PARAMETER structure

## -description

The NDIS_CONFIGURATION_PARAMETER structure contains the data and type of a named entry in the
  registry.

## -struct-fields

### -field ParameterType

The type of the parameter specified as one of the 
     <a href="/windows-hardware/drivers/ddi/configurationparameter/ne-configurationparameter-_ndis_parameter_type">NDIS_PARAMETER_TYPE</a> enumeration values. 
     

For successful calls to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadconfiguration">NdisReadConfiguration</a> function, the    
     <b>ParameterType</b> value matches the value at the 
     <i>ParameterType</i> parameter. However, when the 
     <i>ParameterType</i> parameter is 
     <b>NdisParameterHexInteger</b>, the resulting 
     <b>ParameterType</b> member value is 
     <b>NdisParameterInteger</b>.

### -field ParameterData

A union that contains the value of the given named entry. If ParameterType is a string type, this
      member is an NDIS_STRING type describing a counted string in the system-default character set. For
      Microsoft Windows 2000 and later drivers, such a string contains Unicode characters. That is, for
      Windows 2000 and later, NDIS defines the NDIS_STRING type as a 
      <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> type.

This union contains the following members:

### -field ParameterData.IntegerData

A ULONG value that is used when the 
      <b>ParameterType</b> member is set to 
      <b>NdisParameterInteger</b> or 
      <b>NdisParameterHexInteger</b>.

### -field ParameterData.StringData

An NDIS_STRING value that is used when the 
      <b>ParameterType</b> member is set to 
      <b>NdisParameterString</b> or 
      <b>NdisParameterMultiString</b>.

### -field ParameterData.BinaryData

A <a href="/windows-hardware/drivers/ddi/configurationparameter/ns-configurationparameter-binary_data">BINARY_DATA</a> structure that is used when the <b>ParameterType</b> member is set to <b>NdisParameterBinary</b>.

## -remarks

To read parameters in the registry, an NDIS driver can call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadconfiguration">NdisReadConfiguration</a> function. If
    the call is successful, NDIS returns a pointer to an NDIS_CONFIGURATION_PARAMETER structure at the 
    <i>ParameterValue</i> parameter of 
    <b>NdisReadConfiguration</b>.

To write parameters to the registry, an NDIS driver can call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteconfiguration">NdisWriteConfiguration</a> function. In
    this case, the driver initializes an NDIS_CONFIGURATION_PARAMETER structure and passes it at the 
    <i>ParameterValue</i> parameter of 
    <b>NdisWriteConfiguration</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/configurationparameter/ns-configurationparameter-binary_data">BINARY_DATA</a>

<a href="/windows-hardware/drivers/ddi/configurationparameter/ne-configurationparameter-_ndis_parameter_type">NDIS_PARAMETER_TYPE</a>

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadconfiguration">NdisReadConfiguration</a>

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteconfiguration">NdisWriteConfiguration</a>

<a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>

