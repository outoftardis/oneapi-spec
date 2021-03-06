.. _spr2-usm-version:

spr2 (USM Version)
==================


.. container::


   Computes a rank-2 update of a symmetric packed matrix.


   .. container:: section
      :name: GUID-44B72132-1EC0-41FA-9189-4596CFD651B0


      .. rubric:: Syntax
         :class: sectiontitle


      .. container:: dlsyntaxpara


         .. cpp:function::  event spr2(queue &exec_queue, uplo         upper_lower, std::int64_t n, T alpha, const T \*x, std::int64_t         incx, const T \*y, std::int64_t incy, T \*a)

         The USM version of\ ``spr`` supports the following precisions.


         .. list-table:: 
            :header-rows: 1

            * -  T 
            * -  ``float`` 
            * -  ``double`` 




   .. container:: section
      :name: GUID-3AF7EB4D-B3FE-4C0A-B7A0-6E286D4C642F


      .. rubric:: Description
         :class: sectiontitle


      The spr2 routines compute two scalar-vector-vector products and
      add them to a symmetric packed matrix. The operation is defined as


     


         A <- alpha*x*y :sup:`T` + alpha*y*x :sup:`T` + A


      where:


      ``alpha`` is scalar,


      ``A`` is an ``n``-by-``n`` symmetric matrix, supplied in packed
      form,


      ``x`` and ``y`` are vectors of length ``n``.


   .. container:: section
      :name: GUID-E1436726-01FE-4206-871E-B905F59A96B4


      .. rubric:: Input Parameters
         :class: sectiontitle


      exec_queue
         The queue where the routine should be executed.


      upper_lower
         Specifies whether ``A`` is upper or lower triangular. See
         :ref:`onemkl_datatypes` for
         more details.


      n
         Number of rows and columns of ``A``. Must be at least zero.


      alpha
         Scaling factor for the matrix-vector product.


      x
         Pointer to input vector ``x``. The array holding input vector
         ``x`` must be of size at least (1 + (``n`` - 1)*abs(``incx``)).
         See `Matrix and Vector
         Storage <../matrix-storage.html>`__ for
         more details.


      incx
         Stride of vector ``x``.


      y
         Pointer to input/output vector ``y``. The array holding
         input/output vector ``y`` must be of size at least (1 + (``n``
         - 1)*abs(``incy``)). See `Matrix and Vector
         Storage <../matrix-storage.html>`__ for
         more details.


      incy
         Stride of vector ``y``.


      a
         Pointer to input matrix ``A``. The array holding input matrix
         ``A`` must have size at least (``n``\ \*(``n``-1))/2. See
         `Matrix and Vector
         Storage <../matrix-storage.html>`__ for
         more details.


      dependencies
         List of events to wait for before starting computation, if any.
         If omitted, defaults to no dependencies.


   .. container:: section
      :name: GUID-9796BA93-31FB-40B9-B139-219905913736


      .. rubric:: Output Parameters
         :class: sectiontitle


      a
         Pointer to the updated upper triangular part of the symmetric
         matrix ``A`` if ``upper_lower =upper`` or the updated lower
         triangular part of the symmetric matrix ``A`` if
         ``upper_lower =lower``.


   .. container:: section
      :name: GUID-FE9BC089-7D9E-470F-B1B6-2679FBFC249F


      .. rubric:: Return Values
         :class: sectiontitle


      Output event to wait on to ensure computation is complete.


.. container:: familylinks


   .. container:: parentlink


      **Parent topic:** :ref:`blas-level-2-routines`
      


