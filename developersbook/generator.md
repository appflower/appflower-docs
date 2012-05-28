# The code generator
AppFlower has a code generator similar to the Symfony Admin Generator. In fact, it is an extension of the Symfony task, which means the syntax is very similar and it supports most of the same features.

It also contains AppFlower-specific functionality: it supports more options and the YML syntax is different, too.

## The code generator shell task

Just like Symfony, AppFlower also provides a CLI task, which is an automated module builder.

<pre>
>> symfony appflower:generate-admin [--module="..."] [--singular="..."] [--plural="..."] [--env="..."] [--no-forms="..."] application model
</pre>

As you can see, it has almost the same arguments and options as the SF task, but there are a few differences:


The second argument must be the name of a Model class, routes are NOT supported.
It has one extra option: --no-forms.

The routing names aren't allowed because the generated rules are currently incompatible with AppFlower; however, this restriction should be removed in the near future.

The ***-no-forms*** option is meant to speed up the building process. By default, the generator builds all _Form and Filter_ classes every time you execute it, but if you set this option to "true", the step will be skipped and the process will run a lot faster. time you execute it. If you set this option to "true", this step will be skipped, thus the process will run a lot faster.

Please note that the Form and Filter classes MUST be generated at least once, otherwise the generator won't work properly!

Like I said, the rest of the command line options are the same as Symfony's Admin Generator. For more information, please see:

<pre>
>> symfony help propel:generate-admin
</pre>

When the task is executed, it will generate all necessary files (just like in Symfony), including the generator.yml file, which has the default content. This kind of module is instantly usable (you can access it in your browser). To define the details, look and feel, you must edit the generator.yml file.