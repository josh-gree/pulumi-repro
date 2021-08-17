```
pulumi-repro git:(main) ✗ poetry run python -c 'from pulumi_repro.utils import foo; print(foo(2,3))'
5
```


```
➜  pulumi-repro git:(main) ✗ poetry run pulumi up -y                                                   
Please choose a stack, or create a new one: repro
Previewing update (repro)

View Live: https://app.pulumi.com/josh-gree/pulumi_repro/repro/previews/4271614f-3f62-457a-89fb-72703bd0dc49

     Type                 Name                Plan     Info
     pulumi:pulumi:Stack  pulumi_repro-repro           3 errors
 
Diagnostics:
  pulumi:pulumi:Stack (pulumi_repro-repro):
    error: Program failed with an unhandled exception:
    error: Traceback (most recent call last):
      File "/Users/hj/.pulumi/bin/pulumi-language-python-exec", line 92, in <module>
        loop.run_until_complete(coro)
      File "/Users/hj/.pyenv/versions/3.8.6/lib/python3.8/asyncio/base_events.py", line 616, in run_until_complete
        return future.result()
      File "/Users/hj/Library/Caches/pypoetry/virtualenvs/pulumi-repro-j_azsvbd-py3.8/lib/python3.8/site-packages/pulumi/runtime/stack.py", line 110, in run_in_stack
        await run_pulumi_func(lambda: Stack(func))
      File "/Users/hj/Library/Caches/pypoetry/virtualenvs/pulumi-repro-j_azsvbd-py3.8/lib/python3.8/site-packages/pulumi/runtime/stack.py", line 43, in run_pulumi_func
        func()
      File "/Users/hj/Library/Caches/pypoetry/virtualenvs/pulumi-repro-j_azsvbd-py3.8/lib/python3.8/site-packages/pulumi/runtime/stack.py", line 110, in <lambda>
        await run_pulumi_func(lambda: Stack(func))
      File "/Users/hj/Library/Caches/pypoetry/virtualenvs/pulumi-repro-j_azsvbd-py3.8/lib/python3.8/site-packages/pulumi/runtime/stack.py", line 133, in __init__
        func()
      File "/Users/hj/.pulumi/bin/pulumi-language-python-exec", line 91, in <lambda>
        coro = pulumi.runtime.run_in_stack(lambda: runpy.run_path(args.PROGRAM, run_name='__main__'))
      File "/Users/hj/.pyenv/versions/3.8.6/lib/python3.8/runpy.py", line 282, in run_path
        return _run_code(code, mod_globals, init_globals,
      File "/Users/hj/.pyenv/versions/3.8.6/lib/python3.8/runpy.py", line 87, in _run_code
        exec(code, run_globals)
      File "./__main__.py", line 1, in <module>
        from pulumi_repro.utils import foo
    ModuleNotFoundError: No module named 'pulumi_repro'
    error: an unhandled error occurred: Program exited with non-zero exit code: 1
```