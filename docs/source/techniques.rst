.. currentmodule:: opentuner.search.composableevolutionarytechniques

********************
Current Techniques
********************

OpenTuner has a library of existing search techniques.

=================================
Composable Search Techniques
=================================

A ComposableEvolutionaryTechnique allows for composition between the search technique and any operators. Creating a ComposableEvolutionaryTechnique requires implementing 3 methods:

 * :meth:`minimum_number_of_parents <ComposableEvolutionaryTechnique.minimum_number_of_parents>`
 * :meth:`get_parents <ComposableEvolutionaryTechnique.get_parents>`
 * :meth:`update_population <ComposableEvolutionaryTechnique.update_population>`

Additionally, the following methods may be overridden for further customization

 * :meth:`make_population_member <ComposableEvolutionaryTechnique.make_population_member>`
 * :meth:`select_parameters <ComposableEvolutionaryTechnique.select_parameters>`
 * :meth:`get_default_operator <ComposableEvolutionaryTechnique.get_default_operator>`

The following methods are useful when choosing parents or updating the population:

 * :meth:`lt <ComposableEvolutionaryTechnique.lt>`
 * :meth:`lte <ComposableEvolutionaryTechnique.lte>`
 * :meth:`get_global_best_configuration <ComposableEvolutionaryTechnique.get_global_best_configuration>`

A ComposableEvolutionaryTechnique will yields configurations generated by successive iterations of applying operators on the configurations returned by :meth:`get_parents <ComposableEvolutionaryTechnique.get_parents>` and updating the population with the new configuration through :meth:`update_population <ComposableEvolutionaryTechnique.update_population>`

.. autoclass:: ComposableEvolutionaryTechnique

	.. automethod:: minimum_number_of_parents

	.. automethod:: get_parents

	.. automethod:: update_population

	.. automethod:: make_population_member

	.. automethod:: select_parameters

	.. automethod:: get_default_operator

	.. automethod:: lt

	.. automethod:: lte

	.. automethod:: get_global_best_configuration
