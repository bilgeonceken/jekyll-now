---
layout: post
title: Idea - Usable Clone of Java Serialize, Protobuff
---

1. Transform object structure to binary and read the data in any language you want.
2. Unlike java-serialize this module will only write bytes to a file and thats all. Another alternative would be google protobuf however, i am thinking of a more compact solution.
3. Do not use DataOutputStream since it forces big-indian.
4. Do not forget to support data types that are not available in java.
5. Use JStruct when necessary.
