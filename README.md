# Kucok-koda
//This function uses the qrcode library to generate a QR code

/**
 * Generates a QR code
 * @param {string} data - The data to be encoded in the QR code
 * @param {string} [type='svg'] - The type of QR code to generate. Options are 'svg', 'canvas', 'terminal', or 'img'.
 * @param {object} [options] - Optional options for the QR code. See the qrcode library documentation for more information.
 * @returns {string} - The generated QR code
 */
function generateQRCode(data, type = 'svg', options = {}) {
  try {
    const qrCode = qrcode.create(data, { type, ...options });
    return qrCode.svg();
  } catch (err) {
    console.error(`Error generating QR code: ${err.message}`);
    return '';
  }
}
