---
UID: NA:acpiioct
ms.assetid: 2ccdfa60-af1b-3b60-aaab-f9acba1872c6
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Acpiioct.h header



This header is used by ACPI. For more information, see
- [ACPI](../_acpi/index.md)

Acpiioct.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_ACPI_DEVICE_INFORMATION_OUTPUT_BUFFER structure](ns-acpiioct-_acpi_device_information_output_buffer.md) | The ACPI_DEVICE_INFORMATION_OUTPUT_BUFFER structure contains output arguments from the IOCTL_ACPI_GET_DEVICE_INFORMATION control method. |
| [_ACPI_ENUM_CHILD structure](ns-acpiioct-_acpi_enum_child.md) | The ACPI_ENUM_CHILD structure is a member of the ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure and contains the full path and name of an object in an ACPI namespace. |
| [_ACPI_ENUM_CHILDREN_INPUT_BUFFER structure](ns-acpiioct-_acpi_enum_children_input_buffer.md) | The ACPI_ENUM_CHILDREN_INPUT_BUFFER structure is used as input to an IOCTL_ACPI_ENUM_CHILDREN request. The structure specifies which child objects to enumerate in the namespace of the device to which the request is sent. |
| [_ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure](ns-acpiioct-_acpi_enum_children_output_buffer.md) | The ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure contains an array of object names in an ACPI namespace. |
| [_ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1 structure](ns-acpiioct-_acpi_eval_input_buffer_complex_v1.md) | The ACPI_EVAL_INPUT_BUFFER_COMPLEX structure is used as input to an IOCTL_ACPI_EVAL_METHOD request and to an IOCTL_ACPI_ASYNC_EVAL_METHOD request. The structure supplies the name of a control method and an input array of ACPI_METHOD_ARGUMENT structures. |
| [_ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX structure](ns-acpiioct-_acpi_eval_input_buffer_complex_v1_ex.md) | The ACPI_EVAL_INPUT_BUFFER_COMPLEX_EX structure is used as input to an IOCTL_ACPI_EVAL_METHOD_EX request and to an IOCTL_ACPI_ASYNC_EVAL_METHOD_EX request. |
| [_ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2 structure](ns-acpiioct-_acpi_eval_input_buffer_complex_v2.md) | This topic describes the ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2 structure. |
| [_ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX structure](ns-acpiioct-_acpi_eval_input_buffer_complex_v2_ex.md) | This topic describes the ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX structure. |
| [_ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V1 structure](ns-acpiioct-_acpi_eval_input_buffer_simple_integer_v1.md) | The ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER structure is used as input to an IOCTL_ACPI_EVAL_METHOD request and to an IOCTL_ACPI_ASYNC_EVAL_METHOD request. The structure supplies the name of a control method and an input argument of type ULONG. |
| [_ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V1_EX structure](ns-acpiioct-_acpi_eval_input_buffer_simple_integer_v1_ex.md) | The ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_EX structure is used as input to an IOCTL_ACPI_EVAL_METHOD_EX request and to an IOCTL_ACPI_ASYNC_EVAL_METHOD_EX request. |
| [_ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2 structure](ns-acpiioct-_acpi_eval_input_buffer_simple_integer_v2.md) | This topic describes the ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2 structure. |
| [_ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2_EX structure](ns-acpiioct-_acpi_eval_input_buffer_simple_integer_v2_ex.md) | This topic describes the ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V2_EX structure. |
| [_ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1 structure](ns-acpiioct-_acpi_eval_input_buffer_simple_string_v1.md) | The ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING structure is used as input to an IOCTL_ACPI_EVAL_METHOD request and to an IOCTL_ACPI_ASYNC_EVAL_METHOD request. The structure supplies the name of a control method and an input argument that is an ASCII string. |
| [_ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1_EX structure](ns-acpiioct-_acpi_eval_input_buffer_simple_string_v1_ex.md) | The ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_EX structure is used as input to an IOCTL_ACPI_EVAL_METHOD_EX request and to an IOCTL_ACPI_ASYNC_EVAL_METHOD_EX request. |
| [_ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2 structure](ns-acpiioct-_acpi_eval_input_buffer_simple_string_v2.md) | This topic describes the ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2 structure. |
| [_ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX structure](ns-acpiioct-_acpi_eval_input_buffer_simple_string_v2_ex.md) | This topic describes the ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX structure. |
| [_ACPI_EVAL_INPUT_BUFFER_V1 structure](ns-acpiioct-_acpi_eval_input_buffer_v1.md) | The ACPI_EVAL_INPUT_BUFFER structure is used as input to an IOCTL_ACPI_EVAL_METHOD request and to an IOCTL_ACPI_ASYNC_EVAL_METHOD request. The structure supplies the name of a control method that does not take an input argument. |
| [_ACPI_EVAL_INPUT_BUFFER_V1_EX structure](ns-acpiioct-_acpi_eval_input_buffer_v1_ex.md) | The ACPI_EVAL_INPUT_BUFFER_EX structure is used as input to an IOCTL_ACPI_EVAL_METHOD_EX request and to an IOCTL_ACPI_ASYNC_EVAL_METHOD_EX request. |
| [_ACPI_EVAL_INPUT_BUFFER_V2 structure](ns-acpiioct-_acpi_eval_input_buffer_v2.md) | This topic describes the ACPI_EVAL_INPUT_BUFFER_V2 structure. |
| [_ACPI_EVAL_INPUT_BUFFER_V2_EX structure](ns-acpiioct-_acpi_eval_input_buffer_v2_ex.md) | This topic describes the ACPI_EVAL_INPUT_BUFFER_V2_EX structure. |
| [_ACPI_EVAL_OUTPUT_BUFFER_V1 structure](ns-acpiioct-_acpi_eval_output_buffer_v1.md) | The ACPI_EVAL_OUTPUT_BUFFER structure contains output arguments from an ACPI control method. |
| [_ACPI_EVAL_OUTPUT_BUFFER_V2 structure](ns-acpiioct-_acpi_eval_output_buffer_v2.md) | This topic describes the ACPI_EVAL_OUTPUT_BUFFER_V2 structure. |
| [_ACPI_GET_DEVICE_SPECIFIC_DATA structure](ns-acpiioct-_acpi_get_device_specific_data.md) | The ACPI_GET_DEVICE_SPECIFIC_DATA structure contains input arguments for the IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA control method. |
| [_ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER structure](ns-acpiioct-_acpi_manipulate_global_lock_buffer.md) | This topic describes the ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER structure. |
| [_ACPI_METHOD_ARGUMENT_V1 structure](ns-acpiioct-_acpi_method_argument_v1.md) | The ACPI_METHOD_ARGUMENT structure contains the value of an input or output argument of an ACPI control method. |
| [_ACPI_METHOD_ARGUMENT_V2 structure](ns-acpiioct-_acpi_method_argument_v2.md) | This topic describes the ACPI_METHOD_ARGUMENT_V2 structure. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_ACPI_ACQUIRE_GLOBAL_LOCK IOCTL](ni-acpiioct-ioctl_acpi_acquire_global_lock.md) | The IOCTL_ACPI_ACQUIRE_GLOBAL_LOCK device control request is reserved for internal use only. |
| [IOCTL_ACPI_ASYNC_EVAL_METHOD IOCTL](ni-acpiioct-ioctl_acpi_async_eval_method.md) | A driver for a device can use the IOCTL_ACPI_ASYNC_EVAL_METHOD device control request to asynchronously evaluate an ACPI control method that is supported by the device. |
| [IOCTL_ACPI_ASYNC_EVAL_METHOD_EX IOCTL](ni-acpiioct-ioctl_acpi_async_eval_method_ex.md) | A driver for a device can use the IOCTL_ACPI_ASYNC_EVAL_METHOD_EX device control request to asynchronously evaluate an ACPI control method that is supported by a child device of the device. |
| [IOCTL_ACPI_ASYNC_EVAL_METHOD_V1 IOCTL](ni-acpiioct-ioctl_acpi_async_eval_method_v1.md) | The IOCTL_ACPI_ASYNC_EVAL_METHOD_V1 control code asynchronously evaluates an ACPI control method that is supported by the device. |
| [IOCTL_ACPI_ASYNC_EVAL_METHOD_V1_EX IOCTL](ni-acpiioct-ioctl_acpi_async_eval_method_v1_ex.md) | The IOCTL_ACPI_ASYNC_EVAL_METHOD_V1_EX control code asynchronously evaluates an ACPI control method that is supported by the device. |
| [IOCTL_ACPI_ASYNC_EVAL_METHOD_V2 IOCTL](ni-acpiioct-ioctl_acpi_async_eval_method_v2.md) | The IOCTL_ACPI_ASYNC_EVAL_METHOD_V2 control code asynchronously evaluates an ACPI control method that is supported by the device. |
| [IOCTL_ACPI_ASYNC_EVAL_METHOD_V2_EX IOCTL](ni-acpiioct-ioctl_acpi_async_eval_method_v2_ex.md) | The IOCTL_ACPI_ASYNC_EVAL_METHOD_V2_EX control code asynchronously evaluates an ACPI control method that is supported by the device. |
| [IOCTL_ACPI_ENUM_CHILDREN IOCTL](ni-acpiioct-ioctl_acpi_enum_children.md) | The IOCTL_ACPI_ENUM_CHILDREN device control request can be used to enumerate the path and name of devices or named child objects in the ACPI namespace of the device to which this request is sent. |
| [IOCTL_ACPI_EVAL_METHOD IOCTL](ni-acpiioct-ioctl_acpi_eval_method.md) | A driver for a device can use the IOCTL_ACPI_EVAL_METHOD device control request to synchronously evaluate an ACPI control method that is supported by the device. |
| [IOCTL_ACPI_EVAL_METHOD_EX IOCTL](ni-acpiioct-ioctl_acpi_eval_method_ex.md) | A driver for a device can use the IOCTL_ACPI_EVAL_METHOD_EX device control request to synchronously evaluate an ACPI control method that is supported by a child device in the namespace of the device. |
| [IOCTL_ACPI_EVAL_METHOD_V1 IOCTL](ni-acpiioct-ioctl_acpi_eval_method_v1.md) | The IOCTL_ACPI_EVAL_METHOD_V1 control code synchronously evaluates an ACPI control method that is supported by the device. |
| [IOCTL_ACPI_EVAL_METHOD_V1_EX IOCTL](ni-acpiioct-ioctl_acpi_eval_method_v1_ex.md) | The IOCTL_ACPI_EVAL_METHOD_V1_EX control code synchronously evaluates an ACPI control method that is supported by the device. |
| [IOCTL_ACPI_EVAL_METHOD_V2 IOCTL](ni-acpiioct-ioctl_acpi_eval_method_v2.md) | The IOCTL_ACPI_EVAL_METHOD_V2 control code synchronously evaluates an ACPI control method that is supported by the device. |
| [IOCTL_ACPI_EVAL_METHOD_V2_EX IOCTL](ni-acpiioct-ioctl_acpi_eval_method_v2_ex.md) | The IOCTL_ACPI_EVAL_METHOD_V2_EX control code synchronously evaluates an ACPI control method that is supported by the device. |
| [IOCTL_ACPI_GET_DEVICE_INFORMATION IOCTL](ni-acpiioct-ioctl_acpi_get_device_information.md) | A driver for a device can use the IOCTL_ACPI_GET_DEVICE_INFORMATION device control request to obtain fine-grained identification information about its device. |
| [IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA IOCTL](ni-acpiioct-ioctl_acpi_get_device_specific_data.md) | The IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA control code is used to get device specific data. |
| [IOCTL_ACPI_RELEASE_GLOBAL_LOCK IOCTL](ni-acpiioct-ioctl_acpi_release_global_lock.md) | The IOCTL_ACPI_RELEASE_GLOBAL_LOCK device control request is reserved for internal use only. |
