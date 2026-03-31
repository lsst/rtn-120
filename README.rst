.. image:: https://img.shields.io/badge/rtn--120-lsst.io-brightgreen.svg
   :target: https://rtn-120.lsst.io
.. image:: https://github.com/lsst/rtn-120/workflows/CI/badge.svg
   :target: https://github.com/lsst/rtn-120/actions/

###############################################################################################################
Development of a Retrieval-Augmented Generation Chatbot for Enhanced Information Discovery at Rubin Observatory
###############################################################################################################

RTN-120
=======

The Vera C. Rubin Observatory will generate petabytes of data through the Legacy Survey of Space and Time (LSST) over the next decade, enabling discoveries across a broad range of astrophysical fields. Alongside these data products, Rubin maintains a large but heterogeneous collection of supporting documentation, including operational guides, technical notes, and scientific papers. Because this material is distributed across multiple platforms and formats, staff and scientists often struggle to efficiently locate accurate, up-to-date information. Many resources also reside on internal systems, limiting the ability of general-purpose language models to provide reliable answers to Rubin-specific questions. To address these challenges, we explore the use of Retrieval-Augmented Generation (RAG) to improve information discovery. We present a prototype RAG-based virtual assistant that delivers context-aware, factual, conversational access to Rubin’s vast and heterogenous documentation ecosystem. The system integrates material from multiple sources and enables semantic search through a conversational interface, using Weaviate for embeddings, LangChain for query orchestration, and an OpenAI GPT model as the LLM backend. By grounding responses in domain-specific knowledge, the assistant reduces hallucinations, improves accuracy, and demonstrates the potential of RAG to enhance access to distributed knowledge, streamline workflows, and support effective use of LSST data products.

Links
=====

- Live drafts: https://rtn-120.lsst.io
- GitHub: https://github.com/lsst/rtn-120

Build
=====

This repository includes lsst-texmf_ as a Git submodule.
Clone this repository::

    git clone --recurse-submodules https://github.com/lsst/rtn-120

Compile the PDF::

    make

Clean built files::

    make clean

Updating acronyms
-----------------

A table of the technote's acronyms and their definitions are maintained in the `acronyms.tex` file, which is committed as part of this repository.
To update the acronyms table in ``acronyms.tex``::

    make acronyms.tex

*Note: this command requires that this repository was cloned as a submodule.*

The acronyms discovery code scans the LaTeX source for probable acronyms.
You can ensure that certain strings aren't treated as acronyms by adding them to the `skipacronyms.txt <./skipacronyms.txt>`_ file.

The lsst-texmf_ repository centrally maintains definitions for LSST acronyms.
You can also add new acronym definitions, or override the definitions of acronyms, by editing the `myacronyms.txt <./myacronyms.txt>`_ file.

Updating lsst-texmf
-------------------

`lsst-texmf`_ includes BibTeX files, the ``lsstdoc`` class file, and acronym definitions, among other essential tooling for LSST's LaTeX documentation projects.
To update to a newer version of `lsst-texmf`_, you can update the submodule in this repository::

   git submodule update --init --recursive

Commit, then push, the updated submodule.

.. _lsst-texmf: https://github.com/lsst/lsst-texmf
