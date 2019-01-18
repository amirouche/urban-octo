# urban-octo

experimental background task executor that can handle priorities.

## Process

Simulate various workloads in random but reproducible manner. Take
inspiration from https://youtu.be/4fFDFbi3toc.

## Glossary

- idempotence
- at-least-once
- exactly-once
- starving

## Brainstorming

- A single queue with a single pool of workers that scores tasks based
  on age and priority.

- Priorities: `high`, `normal`, `low`, `idle` (maybe this should be
  customisable by the user (why not integers priorities?!)).

- Store statistics about `enqueue`, `exec` and `complete` times by
  priority, to be able to tell the average time it takes for a task to
  finish.

- Synchronous vs. asynchronous tasks.

- Store task results.

- Each worker is an http server (aiohttp?)

- Keep track of tasks names and do statistic about them

- Different from OS scheduling because distributed

# Ressource

- [Scheduling](https://en.wikipedia.org/wiki/Scheduling_(computing))
- http://www.celeryproject.org/
- https://dramatiq.io/
- https://github.com/Nextdoor/ndkale
- https://github.com/celery/celery/issues/4901
- [Aging](https://en.wikipedia.org/wiki/Aging_(scheduling))
- https://bravenewgeek.com/you-cannot-have-exactly-once-delivery-redux/
- https://grid.cs.gsu.edu/~tcpp/curriculum/?q=system/files/Ch11_0.pdf
- https://www.cs.mcgill.ca/~maheswar/COURSES/ANC2004/PAPERS/Rot94.pdf
- http://eprints.maynoothuniversity.ie/8394/1/TN-Dynamic-2005.pdf
- [Dynamic Task Scheduling with Load Balancing using Hybrid Particle
  Swarm Optimization
  ](http://emis.ams.org/journals/IJOPCM/Vol/09/IJOPCM(vol.2.3.12.S.9).pdf)
- https://www.computer.org/csdl/proceedings/pccc/1994/1814/00/00504094.pdf
- http://thesai.org/Downloads/Volume8No1/Paper_4-Analysis_of_Particle_Swarm_Optimization_and_Genetic_Algorithm.pdf
