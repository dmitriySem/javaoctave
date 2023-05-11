JavaOctave
==========

Downstream fork of [JavaOctave](https://kenai.com/projects/javaoctave/pages/Home)


import dk.ange.octave.OctaveEngine;
import dk.ange.octave.OctaveEngineFactory;
import dk.ange.octave.type.OctaveDouble;

OctaveEngine octave = new OctaveEngineFactory().getScriptEngine();
OctaveDouble matA = new OctaveDouble(new double[] {1,2,3,4,5,6,7,8,9,10,11,12,13,14,15}, 3, 5);
octave.put("a", matA);
octave.eval("a");

String matB = "b = [1,2,3; 4,5,6; 7,8,9]";
octave.eval(matB);

octave.eval("x = b(1,:)");
OctaveDouble varX = (OctaveDouble) octave.get("x");
System.out.println("Result: "+varX.get(1)+" "+varX.get(2)+" "+varX.get(3));
octave.close();

______________________
a =

    1    4    7   10   13
    2    5    8   11   14
    3    6    9   12   15

b =

   1   2   3
   4   5   6
   7   8   9

Result: 1.0 2.0 3.0
