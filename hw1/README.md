# CS294-112 HW 1: Imitation Learning

This is the code for the first problem set from Berkeley's cs294, modified to
work with the free RoboSchool engine, rather than Mujoco. The original pset
came with expert models. Instead of these, we'll use the pre-trained models
that come in the agent_zoo/ subdirectory of the RoboSchool distribution.

Dependencies: TensorFlow, RoboSchool, OpenAI Gym

1. Install OpenAI gym as described at https://gym.openai.com/docs
1. Build bullet3 and install RoboSchool as at https://github.com/openai/roboschool
    * Gotcha #1: link error missing -lpython_boost-py3. Fix BOOST_PYTHON3_POSTFIX = 3 in roboschool/cpp-household/Makefile.
    * Gotcha #2: Segfault on run. See https://github.com/openai/roboschool/issues/29

The only file that you need to look at is `run_expert.py`, which is code to load up an expert policy and run a specified number of roll-outs. Run with e.g.

    python run_expert.py roboschool/agent_zoo/RoboschoolHalfCheetah_v0_2017may.py \
        RoboschoolHalfCheetah-v0 --render --num_rollouts 20
