# Spherical rotation (permutation) of a parcellated cortical map

**Note**: *I am grateful to Aaron Alexander-Bloch for recently (June 2019) bringing to my attention that the permutation approach implemented here is biased, and does not uniformly sample the space of permutations on the sphere. For details, see description and references within the document "technical_note_18July2018.docx" at https://github.com/spin-test/spin-test. Until the code provided here has been updated to correct for this bias, please use with caution.*

Code (in Matlab and R) to perform a spherical rotation (permutation) of a parcellated cortical map. 

Includes coordinates on the Freesurfer sphere of 360 regions from the Glasser et al. *Nature* 2016 HCP parcellation.

For details on this specific implementation of the code, see the Váša et al. *Cerebral Cortex* manuscript referenced below; and in particular the supplementary information section "Spatial permutation test".

## Code

Each version (Matlab and R) contains two functions: rotate_parcellation and perm_sphere_p. 

**rotate_parcellation** generates a desired number of rotated permutations of a parcellation, given the coordinates of left and right hemispheres of this parcellation on the sphere.

**perm_sphere_p** generates a permutation p-value, given two parcellated cortical maps to be compared, a set of permutations (generated by rotate_parcellation) and the desired type of correlation to compare the cortical maps (eg: Spearman).

Additionally included is **centroid_extraction_sphere**, a Matlab function to obtain spherical coordinates of regional centroids from Freesurfer .annot files, for any parcellation (written by Rafael Romero-Garcia).

For specific instructions, see the code.

## Example

![Spherical permutation example](/spherical_permutation_example.png)

The spatial permutation test was applied three times to cortical maps of the x, y and z coordinates of regional centroids in MNI space. The spatial contiguity and hemispheric symmetry is preserved within the permuted maps.

## References

This specific implementation of the code was developed specifically for parcellated cortical maps, and was first applied in the following paper:

  * Váša F., Seidlitz J., Romero-Garcia R., Whitaker K. J., Rosenthal G., Vértes P. E., Shinn M., Alexander-Bloch A., Fonagy P., Dolan R. J., Goodyer I. M., the NSPN consortium, Sporns O., Bullmore E. T. (2017). Adolescent tuning of association cortex in human structural brain networks. *Cerebral Cortex*, 28(1):281–294.

However, the idea of a spherical rotation (permutation) was first proposed for vertex-level cortical maps, and first applied (to the best of my knowledge) in the following paper:

  * Alexander-Bloch, A., Raznahan, A., Bullmore, E., and Giedd, J. (2013). The convergence of maturational change and structural covariance in human cortical networks. *Journal of Neuroscience*, 33(7):2889–99.

The same idea was subsequently explored in other papers.

Finally, the idea was more formally discussed in the following paper, where the methods (for vertex-wise analyses) are made publicly available as well: 

  * Alexander-Bloch, A., Shou H., Liu, S., Satterthwaite, T. D., Glahn, D. C., Shinohara, R. T., Vandekar, S. N. and Raznahan, A. (2018). On testing for spatial correspondence between maps of human brain structure and function. *NeuroImage*, 178:540-551.
  
For code to perform spherical permutations at the vertex level, see https://github.com/spin-test/spin-test.
