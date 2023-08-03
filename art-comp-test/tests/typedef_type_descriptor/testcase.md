---
group: cpp_code_generation
---
A typedef or type alias with the [[rt::auto_descriptor]] attribute set means that a type descriptor will be automatically generated for it. This is useful if you have an external type that you cannot modify, but still need to use that type in your Art application. The generated type descriptor can be customized by providing custom type descriptor functions. For example, this is needed if the type needs to be encoded/decoded since it's not possible to provide a generic implementation for that. In this example we create a typedef and type alias for std::string and std::vector<int> respectively, and write a custom encode function for them. Other type descriptor functions (except decode) are automatically generated which means we can send an event with these types from one capsule to another. When received, we use the encode functions of the type descriptors to get a string representation of the types.