---
title: Welcome to Our Site
---
{{< blocks/cover title="Welcome to STAP-Zoo" image_anchor="center" height="min" color="primary" >}}
<p class="lead">The Central Repository for Symmetric Techniques for Advanced Protocols</p>
{{< blocks/link-down color="info" >}}
{{< /blocks/cover >}}


{{< blocks/section color="white" type="row" >}}
  <div class="col-md-3 d-flex align-items-center">
    <img src="background300x300.webp" alt="STAP-Zoo Logo" class="img-fluid rounded">
  </div>

  <div class="col-md-9">
    <h2 class="mt-0">What is STAP?</h2>
    <p class="lead">
      The term <strong>STAP</strong> (Symmetric Techniques for Advanced Protocols) was first introduced in STAP’23, an affiliated workshop of Eurocrypt’23.
    </p>
    <p>
      It generally refers to algorithms in symmetric cryptography specifically designed to be efficient in new advanced cryptographic protocols. These contexts include:
    </p>
    <ul>
        <li>Zero-knowledge (ZK) proofs</li>
        <li>Secure multiparty computation (MPC)</li>
        <li>(Fully) homomorphic encryption (FHE)</li>
    </ul>
    <p>It encompasses everything from arithmetization-oriented hash functions to homomorphic encryption-friendly stream ciphers.</p>
  </div>
{{< /blocks/section >}}

{{< blocks/section color="light" >}}
<div class="row">
  <div class="col-12 text-center mb-5">
    <h2>The STAP Zoo Collection</h2>
    <p class="lead">A repository of symmetric primitives designed for advanced cryptographic protocols.</p>
  </div>
</div>

<div class="row">
  <div class="col-md-6">
    <h3>Exploring the Zoo</h3>
    <p>We present a collection of proposed symmetric primitives fitting the STAP description and keep track of recent advances regarding their security and consequent updates.</p>
    
    <ul class="list-unstyled">
      <li class="mb-3"><strong><i class="fas fa-layer-group text-primary mr-2"></i> Primitive Types:</strong> Block Ciphers, Stream Ciphers, Hash Functions, and PRFs.</li>
      <li class="mb-3"><strong><i class="fas fa-shield-alt text-primary mr-2"></i> Use-Cases:</strong> FHE (Fully Homomorphic Encryption), MPC (Secure Multi-Party Computation), and ZK (Zero-Knowledge).</li>
    </ul>
  </div>

  <div class="col-md-6">
    <div class="card shadow-sm border-0 bg-white p-4">
      <h4 class="card-title h5">What we provide for each primitive:</h4>
      <hr>
      <ul class="mb-0">
        <li><strong>Origins:</strong> Designers, year, and original publication.</li>
        <li><strong>Design:</strong> Cryptographic properties, diagrams, and parameters.</li>
        <li><strong>Security:</strong> Known attacks, weaknesses, and security margins.</li>
        <li><strong>Efficiency:</strong> Hardware implementation metrics.</li>
        <li><strong>Lineage:</strong> Relations between different designs.</li>
      </ul>
    </div>
  </div>
</div>
{{< /blocks/section >}}



{{< blocks/section color="white" >}}
<div class="row justify-content-center">
  <div class="col-md-8 text-center">
    
    <div class="p-4 border rounded bg-light shadow-sm">
      <p class="mb-3">If you wish to cite this project, please use the BibTeX entry below:</p>
      
      <div class="position-relative">
        <pre id="bibtex-code" class="text-left bg-dark text-white p-3 rounded" style="font-size: 0.85rem; cursor: pointer;" title="Click to copy">
@misc{stapzoo2026,
  title  = {STAP-Zoo: Symmetric Techniques for Advanced Protocols},
  author = {STAP-Zoo Team},
  year   = {2026},
  url    = {https://stap-zoo.example.org}
}</pre>
        <button id="copy-btn" class="btn btn-sm btn-primary position-absolute" style="top: 10px; right: 10px;">
          <i class="fas fa-copy"></i> Copy
        </button>
      </div>

      <p class="mt-3 small">
        Read more about credits on our <a href="/about-us/">About Us</a> page.
      </p>
    </div>

    <div class="status-disclaimer mt-5">
      <p class="text-uppercase font-weight-bold tracking-wider text-secondary" style="letter-spacing: 2px;">
        <i class="fas fa-hammer mr-2"></i> The website is still under active development
      </p>
      <p class="text-muted small">We are constantly adding new primitives and updating security analysis. Check back often!</p>
    </div>

  </div>
</div>

<script>
  const copyBtn = document.getElementById('copy-btn');
  const bibtex = document.getElementById('bibtex-code');

  const copyToClipboard = () => {
    const text = bibtex.innerText;
    navigator.clipboard.writeText(text).then(() => {
      // Feedback UI
      const originalText = copyBtn.innerHTML;
      copyBtn.innerHTML = '<i class="fas fa-check"></i> Copied!';
      copyBtn.classList.replace('btn-primary', 'btn-success');
      
      setTimeout(() => {
        copyBtn.innerHTML = originalText;
        copyBtn.classList.replace('btn-success', 'btn-primary');
      }, 2000);
    });
  };

  copyBtn.addEventListener('click', copyToClipboard);
  bibtex.addEventListener('click', copyToClipboard);
</script>
{{< /blocks/section >}}