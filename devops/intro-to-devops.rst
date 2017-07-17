======================
Introduction to DevOps
======================

Most people who come this guide will have heard about it from a friend. They
normally need help with some component in their code, or want to know how to use
a specific sensor.

Some of you come here to learn to code to begin with. These people have a long
road ahead of them, and I encourage them to keep going.

Some of you are here because you wish to learn to code better. For you, this is
the wrong chapter, but I will point you to my section on `Code Design and Architecture`_.

And lastly, some of you here are Software leads or Mentors, some of whom are on
either new teams, or thinking their workflows can be optimized for their sub-
team.
This guide is built for these people. The people who wish to improve
development workflow, to better their build systems, and to clean up their codebase,
and to make their lives as maintainers *much* easier.

What is DevOps?
---------------

First we must establish the obvious, **DevOps** is a "clipped compound" of the
words ***development*** and ***operations***. This lends credence to what it
actually means. DevOps as a term was first coined at an Agile software conference
in 2008, who's name was popularized due to a series of "devopsdays" in 2009,
but we don't care about the history of the term, we are here to learn about what
DevOps *is*.


DevOps
------
DevOps is a blanket term that encompasses many aspects of the software development cycle.
As you can see in **Figure 1**. It is often described as the combination of many aspects of
development, quality assurence, and general operations.

.. figure:: ../devops/media/Devops.png
    :width: 320px
    :align: center
    :alt: Binary Image
    :figclass: align-center

        **Figure 1**

        A Venn Diagram showing the crossing between *development*, *QA*, and *Operations*,
        as "DevOps".

        Image by `Rajiv.Pant <https://commons.wikimedia.org/w/index.php?title=User:Rajiv.Pant&action=edit&redlink=1>`_,
        derieved from `Wylve <https://commons.wikimedia.org/wiki/User:Wylve>`_ /
        `CC BY 3.0 <http://creativecommons.org/licenses/by/3.0>`_

.. topic:: DevOps Toolchains

    A "toolchain", is really a set of tools intended for use with DevOps. These
    tools cover a wide array of uses, as DevOps is such an encompassing field.
    Tools typically fall into a few different catagories, as can be seen below in
    **Figure 2**. For a quick breakdown of the DevOps "toolchain" flow, see **Figure 3**

    +---------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
    | Design Phase  | Meaning                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
    +---------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
    | Plan          | The planning phase is  pretty straight forward, but this is where much time will be spent. Planning is a key step in the design process, and should not be downplayed.                                                                                                                                                                                                                                                                                                    |
    +---------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
    | Create        | This is the beginning development phase; where you and your team begin code synthesis. This is often regarded as the most important part, but as we see later, it is merely a small part in the bigger picture.                                                                                                                                                                                                                                                           |
    +---------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
    | Verify/Test   | One of the ***most*** important, yet most annoying phases of the entire development process, is insuring the code does what it is supposed to do. This can be accomplished in a variety of ways, but the way it is typically handled, is by designing through `Test Driven Design`.                                                                                                                                                                                       |
    +---------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
    | Package       | Pre-deployment phase. After you pass the tests, you must have your code ready to ship, or in our case, deploy to our robot at the end of build season. This is normally the last phase that any developers would stop at.                                                                                                                                                                                                                                                 |
    +---------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
    | Release       | This phase seems pretty simple, but it isn't as small as it seems. This isn't just the merge into master that we've all been waiting 6 weeks for, no. This is where we finalize the code is ready, re-run the tests until we feel comfortable, and then finally push to the RoboRIO.                                                                                                                                                                                      |
    +---------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
    | Configuration | This step is also pretty obvious in our case. Tuning your teams robot, calibrating sensors, and ensuring the code will be able to run to its full potential by ensuring our vessel is functional.                                                                                                                                                                                                                                                                         |
    +---------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
    | Monitor       | This phase is where all the improvements happen in your code. This is when your robot is out there preforming, kicking butt, or perhaps breaking for some of us. This is the time where you watch, make notes of what happened, and prepare to begin this cycle all over again with planning, so as to preserve the good development cycle you have built up, as well as fixing the issues that exist in your code currently. Or you can blame mechanical. That's ok too. |
    +---------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

**Figure 2**
A table depicting the various stages of the DevOps "toolchain" flow, and a short
description of each phase.

.. figure:: ../devops/media/Devops-toolchain.png
    :width: 320px
    :align: center
    :alt: Binary Image
    :figclass: align-center

        **Figure 3**

        Illustration showing the stages in a DevOps "toolchain", which we will touch on later.

        Image by `Kharnagy <https://commons.wikimedia.org/w/index.php?title=User:Kharnagy&action=edit&redlink=1>`_ /
        `CC BY-SA 4.0 <http://creativecommons.org/licenses/by-sa/4.0>`_
