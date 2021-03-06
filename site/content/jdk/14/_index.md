---
title: Java 14
type: sandbox
---

{{< jdkdetails "14" >}}

## New Features

### JVM

* NUMA-Aware Memory Allocation for G1 ([JEP 345](http://openjdk.java.net/jeps/345)) 
* JFR Event Streaming ([JEP 349](http://openjdk.java.net/jeps/349))
* Helpful NullPointerExceptions ([JEP 358](http://openjdk.java.net/jeps/358))
* Deprecate the Solaris and SPARC Ports ([JEP 362](http://openjdk.java.net/jeps/362)) 
* Remove the Concurrent Mark Sweep (CMS) Garbage Collector ([JEP 363](http://openjdk.java.net/jeps/363))
* ZGC on macOS ([JEP 364](http://openjdk.java.net/jeps/364)) 
* ZGC on Windows ([JEP 365](http://openjdk.java.net/jeps/365)) 
* Deprecate the ParallelScavenge + SerialOld GC Combination ([JEP 366](http://openjdk.java.net/jeps/366)) 

### Language

* Pattern Matching for instanceof (Preview) ([JEP 305](http://openjdk.java.net/jeps/305))
* Records (Preview) ([JEP 359](http://openjdk.java.net/jeps/359))
* Switch Expressions (Standard) ([JEP 361](http://openjdk.java.net/jeps/361))
* Text Blocks (Second Preview) ([JEP 368](http://openjdk.java.net/jeps/368))
* Foreign-Memory Access API ([JEP 370](http://openjdk.java.net/jeps/370)) 

### Library

* Non-Volatile Mapped Byte Buffers ([JEP 352](http://openjdk.java.net/jeps/352))
* Remove the Pack200 Tools and API ([JEP 367](http://openjdk.java.net/jeps/367))

### Tools

* Packaging Tool (Incubator) ([JEP 343](http://openjdk.java.net/jeps/343))


## Sandbox

Instantly compile and run Java 14 snippets without a local Java installation.

{{< sandbox version="java14" mainclass="Java14" preview="false" >}}
{{< sandboxsource "Java14.java" >}}
import java.time.DayOfWeek;
import java.time.LocalDate;

public class Java14 {
    
    public static void main(String[] args) {

        String when = switch(DayOfWeek.from(LocalDate.now())) {
            case MONDAY:
                yield "at the beginning of the week";
            case TUESDAY:
            case WEDNESDAY:
            case THURSDAY:
                yield "in the middle of the week";
            case FRIDAY:
                yield "at the end of the week";
            case SATURDAY:
            case SUNDAY:
                yield "at the weekend";
        };

        System.out.printf("Java 14 %s!", when);
    }

}
{{< /sandboxsource >}}
{{< /sandbox >}}

